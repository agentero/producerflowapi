# Webhook

## Table of Contents

- [Webhook](#webhook)
  - [Table of Contents](#table-of-contents)
  - [1. Introduction](#1-introduction)
  - [2. System Overview](#2-system-overview)
  - [3. Webhook Integration Overview](#3-webhook-integration-overview)
    - [Key Requirements](#key-requirements)
  - [4. Webhook Configuration](#4-webhook-configuration)
  - [5. Event Mechanics and Types](#5-event-mechanics-and-types)
    - [Creation Events](#creation-events)
    - [Update Events](#update-events)
    - [Resync Events](#resync-events)
  - [6. Webhook Payload](#6-webhook-payload)
    - [Key Elements](#key-elements)
  - [7. Response and Retries](#7-response-and-retries)
  - [8. Error Handling and Troubleshooting](#8-error-handling-and-troubleshooting)
  - [9. Security Considerations](#9-security-considerations)
  - [10. Signature Verification](#10-signature-verification)
  - [11. Frequently Asked Questions](#11-frequently-asked-questions)

## 1. Introduction

This document provides detailed instructions for integrating your system to receive changes in Producerflow via webhooks. Webhooks allow your system to receive real-time updates whenever changes occur in our system. This guide will cover how to configure your webhook, the expected data format, and how to handle notifications effectively.

## 2. System Overview

Our system processes various types of data changes, such as producer and agency creation using the API, changes coming from NIPR, or manual updates in the Producerflow portal. By integrating with our Webhook system, you can stay in sync with these updates automatically.

## 3. Webhook Integration Overview

A Webhook is an HTTP callback that is triggered when a specified event occurs in our system. You can configure your own Webhook URL, to which our system will send notifications whenever a relevant change happens. These notifications will include a payload containing information about the change.

### Key Requirements

- **Endpoint**: You will provide an HTTPS endpoint for us to call when an event occurs.
- **Timeout**: Webhook calls must be processed within **10 seconds**.
- **Retries**: If a call fails, we will retry up to **3 times**.

## 4. Webhook Configuration

To configure the webhook:

1. Provide an HTTPS endpoint URL
2. Ensure your endpoint can handle POST requests
3. Implement proper response handling (return 2xx status codes for success)
4. Set up appropriate error handling and logging

## 5. Event Mechanics and Types

### Creation Events

- Creation events for all agencies, producers and contacts will be a unique event of type Created.
- It will contain all information sections documented below per entity if there is data available for them
- For example if no background check was triggered for a producer that section will not be included

### Update Events

- Update events will be sent every time there is a change in field belonging to any of the actions described below per entity
- The update event will only contain the data from the section that has undergone the change (as well as the top level fields that each event contains)
- The event type will be Updated

### Resync Events

- A resync event can be triggered manually from the Producerflow UI for any of the entities
- This will trigger a similar event to the creation one that will contain all information sections documented below per entity if there is data available for them
- The event type will be Resync

## 6. Webhook Payload

When a change occurs in a producer, an agency or a contact, we will send a request with a JSON in the request body with the new information of the dimension that has changed.

All messages will include the following common fields giving information about the change:
    - **id**: this is a unique identifier of the event
    - **change_type**: it is the type of change done to the thing. One of “Created", "Updated", "Deleted", “Resync”
    - **origin**: what part of Producerflow did the change. One of "API", "Portal", "NIPR".
    - **timestamp**: when the change happened in Producerflow.

Besides the common fields, and depending on the type of entity that has changed, we will send specific fields describing the entity itself based on the schemas found on the Appendix A of this document.

### Key Elements

- **Agency Identifier Fields**:
  - All three types of messages will include an agency_id field. For agency messages, this field identifies the agency itself. For producer and contact messages, it identifies the agency they are associated with.
  - If available, all three types of messages will include an agency_external_id field. This field represents the agency’s identifier in the tenant system, provided the tenant has supplied it to ProducerFlow.
- **Producer Identifier Field**:
  - For producer messages, we will include a producer_external_id field, which represents the producer’s identifier in the tenant system, provided the tenant has supplied it to ProducerFlow.
- **Origin Field**:
  - The origin field will indicate the source of the change and will take one of the following values:
    - ProducerFlowAPI: Changes made using the public API of ProducerFlow, typically by tenant systems or scripts.
    - ProducerFlowPortal: Changes made in the ProducerFlow Portal, either by a tenant administrator or by an agency user with access to their data in ProducerFlow.
    - NIPR: Changes originating from NIPR and received by ProducerFlow.
- **Partial Payloads for Updates**:
  - To limit the size of the payload, producer and agency events will only contain the information from the section that has undergone the change:
    - An agency has the following sections:
      - agency_data:  general agency attributes collected in the Portal
      - agency_bank_account: bank account information of the agency
      - agency_eo: details about the agency E&O provided during the onboarding
      - agency_ivans_account: IVANS account of the agency
      - agency_address: address of the agency collected in the Portal
      - agency_nipr_data: agency attributes collected from NIPR
      - agency_nipr_appointments: agency appointments in NIPR
      - agency_nipr_licenses: agency licenses in NIPR
      - agency_nipr_addresses: agency addresses in NIPR
    - A producer has the following sections:  
      - producer_data: producer attributes collected in the Portal
      - accurate_background_check: information provided by Accurate about the background check on the producer, if any
      - producer_nipr_data: producer attributes collected from NIPR
      - producer_nipr_appointments: producer appointments in NIPR
      - producer_nipr_licenses: producer licenses in NIPR
      - producer_nipr_addresses: producer addresses in NIPR

## 7. Response and Retries

Your system must respond to our Webhook call with an HTTP status code within **10 seconds**.  

Expected Response:

- **Success (200 OK)**: The request was processed successfully.
- **Failure**: If the request cannot be processed, a status code in the 4xx or 5xx range should be returned.

If the response is a failure or if the 10-second deadline is exceeded, our system will retry the Webhook call up to **two more times using exponential backoff**. This means there will be progressively longer delays between retry attempts.

If all retries fail, the event will be marked as **undelivered**. Undelivered events will not be retried again, and they will be discarded. In the future we will add a way to check for undelivered events in the API.

**Event Redelivery Semantics**:

- Once an event is successfully acknowledged (200 OK), **no further redelivery will occur**.
- While an event is outstanding (not yet acknowledged or deadline expired), **no additional redeliveries** will be initiated.

**Exponential Backoff for Retries**:

Exponential backoff is a strategy where the time between retries increases progressively. In this case, if the initial Webhook call fails, the retries will follow these delays:

- **First retry**: After 1 minute.
- **Second retry**: After an additional **5 minutes**.

This strategy helps to avoid overwhelming your system and allows it time to recover in case of transient failures.

**Flow Control**:

To prevent overloading your system, we will limit the number of outstanding events (i.e., events that are not yet acknowledged) to **100**. Once this limit is reached, no new events will be delivered until some outstanding events are acknowledged or marked as failed.

This mechanism ensures that your system does not become overwhelmed by too many concurrent requests and helps maintain stability under high load.

## 8. Error Handling and Troubleshooting

To ensure smooth operation:

- Log all incoming Webhook requests and responses.
- Handle errors gracefully in your system by using appropriate status codes.
- Check your server’s capacity to process the payload within the given 10-second window.

Common issues include:

- **Timeouts**: Ensure your system can handle large payloads or complex processing efficiently.
- **Incorrect Responses**: Returning status codes other than 200 OK may trigger retries.

## 9. Security Considerations

To ensure secure communication and data protection, we expect the following measures:
    - **HTTPS Only**: Use SSL/TLS-encrypted endpoints to secure data transmission and prevent eavesdropping.
    - **Signature Verification**: Implement HMAC-based signature verification using the shared secret that you can find in the Producerflow portal to authenticate the integrity of incoming requests.
    - **IP Whitelisting** (optional): Restrict incoming requests to trusted IP addresses from our infrastructure to further enhance security.

## 10. Signature Verification

To ensure the integrity and authenticity of the events sent to your webhook endpoint, we use HMAC-based signatures. Each request from our service includes a signature header that allows you to verify that the request originated from us and has not been tampered with.

How It Works:

1. **Shared secret**: ProducerFlow generates a unique shared secret that could be retrieved using the admin portal. This secret is going to be used to sign request payload. Clients must use this secret to verify the integrity of the incoming request. Secret can be retrieved from the Admin portal in the settings page.
2. **Signature header**: ProducerFlow provides a request header ["Producerflow-Signature"] for each request.The hash is generated using HMAC-SHA256 with the shared secret and the request body. Clients must verify signatures using the shared secret.
3. **Verification Process**:
    - Step 1: Extract Producerflow-Signature from the incoming request
    - Step 2: Generate a hash using the HMAC-SHA256 algorithm with the shared secret and the raw request body.
    - Step 3: Compare the generated hash with the value in the Producerflow-Signature header.
    - Step 4: If the hashes match, the request is verified. If they do not match, reject the request as it may have been tampered with.

Appendix B contains some examples of how to verify request signature.

## 11. Frequently Asked Questions

**Q1**: What happens if my Webhook is down during an event?
**A1**: We will attempt to retry the Webhook call up to 3 times before marking it as undelivered.
**Q2**: Can I send a delayed response?
**A2**: Responses must be returned within 10 seconds; otherwise, the request will be considered failed.
