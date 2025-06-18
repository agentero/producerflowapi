# Webhooks Documentation

This directory contains webhook payload documentation for the ProducerFlow API. Webhooks are HTTP callbacks that notify your application when specific events occur within the ProducerFlow system.

## Overview

ProducerFlow webhooks deliver real-time notifications for changes to:

- **Agencies** - Insurance agency information and licensing data
- **Producers** - Individual producer/agent information and licensing data  
- **Contacts** - Contact information for agency personnel

Each webhook payload contains structured data that follows JSON Schema specifications for validation and documentation purposes.

## Webhook Types

### Agency Webhooks

Triggered when agency data is created, updated, or synchronized from external sources.

**Schema**: [agency_schema.json](./schema/agency_schema.json)  
**Example Payload**: [agency_example.json](./examples/agency_example.json)

**Event Types:**

- `agency.created` - New agency record created
- `agency.updated` - Existing agency record modified
- `agency.synced` - Agency data synchronized from NIPR

**Key Data Included:**

- Basic agency information (name, contact details, website)
- Federal Employer Identification Number (FEIN) and National Producer Number (NPN)
- Business addresses and bank account information
- Errors & Omissions insurance details
- IVANS account configuration
- NIPR licensing data including appointments and licenses
- Lines of Authority (LOA) information

### Producer Webhooks

Triggered when producer/agent data is created, updated, or synchronized.

**Schema**: [producer_schema.json](./schema/producer_schema.json)  
**Example Payload**: [producer_example.json](./examples/producer_example.json)

**Event Types:**

- `producer.created` - New producer record created
- `producer.updated` - Existing producer record modified
- `producer.synced` - Producer data synchronized from NIPR

**Key Data Included:**

- Personal information (name, contact details, addresses)
- National Producer Number (NPN) and agency associations
- Background check results from Accurate Background
- NIPR licensing data including appointments and licenses
- Lines of Authority (LOA) and continuing education status
- License expiration dates and compliance information

### Contact Webhooks

Triggered when contact information is created, updated, or deleted.

**Schema**: [contact_schema.json](./schema/contact_schema.json)  
**Example Payload**: [contact_example.json](./examples/contact_example.json)

**Event Types:**

- `contact.created` - New contact record created
- `contact.updated` - Existing contact record modified
- `contact.deleted` - Contact record removed

**Key Data Included:**

- Contact personal information (name, email, phone)
- Physical address information
- Role within the agency
- Associated agency and external identifiers
- National Producer Number (NPN) if applicable

## Common Payload Structure

All webhook payloads share a common base structure:

```json
{
  "id": "string",              // Unique identifier for this change event
  "event_type": "string",      // Specific event type (e.g., "agency.updated")
  "change_type": "string",     // Legacy field: "Created", "Updated", "Deleted"
  "origin": "string",          // Source: "ProducerFlowAPI", "ProducerFlowPortal", "NIPR"
  "timestamp": "string",       // ISO 8601 datetime when change occurred
  // ... entity-specific data
}
```

## Data Origins

Webhook data can originate from multiple sources:

- **ProducerFlowAPI** - Changes made via API calls
- **ProducerFlowPortal** - Changes made through the web portal
- **NIPR** - Data synchronized from the National Insurance Producer Registry

## Schema Validation

All webhook payloads conform to JSON Schema Draft 2020-12 specifications. You can use the provided schema files to:

- Validate incoming webhook payloads
- Generate code/types for your programming language
- Understand the complete data structure and requirements

## Required Fields

Each webhook type has specific required fields:

- **Agency**: `id`, `timestamp`, `agency_id`
- **Producer**: `id`, `timestamp`, `producer_id`  
- **Contact**: `id`, `timestamp`, `contact_id`

## Integration Tips

1. **Idempotency**: Use the `id` field to handle duplicate webhook deliveries
2. **Filtering**: Check `event_type` to process only relevant events
3. **Validation**: Validate payloads against the provided JSON schemas
4. **Error Handling**: Implement retry logic for failed webhook processing
5. **Security**: Verify webhook signatures (implementation-specific)

## NIPR Data

Many webhooks include NIPR (National Insurance Producer Registry) data, which provides:

- Licensed insurance producer information
- Appointment details with insurance carriers
- Lines of Authority (LOA) authorizations
- Continuing Education (CE) compliance status
- License expiration and renewal dates

This data is critical for compliance and regulatory reporting in the insurance industry.

For additional API documentation and integration guides, please refer to the main [API documentation](../wiki/Webhooks.md.md).
