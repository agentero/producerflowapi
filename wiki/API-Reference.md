
# Producerflow API Reference

# Table of Contents


- Services
    - [AppointmentService](#producerflowappointmentv1appointmentservice)
  


- Messages
    - [Appointment](#appointment)
    - [CheckAppointmentEligibilityRequest](#checkappointmenteligibilityrequest)
    - [CheckAppointmentEligibilityResponse](#checkappointmenteligibilityresponse)
    - [GetAppointmentFeesRequest](#getappointmentfeesrequest)
    - [GetAppointmentFeesResponse](#getappointmentfeesresponse)
    - [GetAppointmentRequest](#getappointmentrequest)
    - [GetAppointmentResponse](#getappointmentresponse)
    - [GetTerminationFeesRequest](#getterminationfeesrequest)
    - [GetTerminationFeesResponse](#getterminationfeesresponse)
    - [ListAppointmentsRequest](#listappointmentsrequest)
    - [ListAppointmentsResponse](#listappointmentsresponse)
    - [RequestAppointmentRequest](#requestappointmentrequest)
    - [RequestAppointmentResponse](#requestappointmentresponse)
    - [TerminateAppointmentRequest](#terminateappointmentrequest)
    - [TerminateAppointmentResponse](#terminateappointmentresponse)
  


- Enums
    - [AppointmentType](#appointmenttype)
    - [EligibilityStatus](#eligibilitystatus)
    - [ProcessingStatus](#processingstatus)
  



- Services
    - [ProducerService](#producerflowproducerv1producerservice)
  


- Messages
    - [Address](#address)
    - [Agency](#agency)
    - [Agency.Address](#agencyaddress)
    - [Agency.AgencyInfo](#agencyagencyinfo)
    - [Agency.BankAccount](#agencybankaccount)
    - [Agency.EOInfo](#agencyeoinfo)
    - [Agency.IvansAccount](#agencyivansaccount)
    - [Agency.Principal](#agencyprincipal)
    - [ApproveProducerRequest](#approveproducerrequest)
    - [ApproveProducerResponse](#approveproducerresponse)
    - [CreateAgencyOnboardingURLRequest](#createagencyonboardingurlrequest)
    - [CreateAgencyOnboardingURLRequest.Agency](#createagencyonboardingurlrequestagency)
    - [CreateAgencyOnboardingURLRequest.Agency.Principal](#createagencyonboardingurlrequestagencyprincipal)
    - [CreateAgencyOnboardingURLResponse](#createagencyonboardingurlresponse)
    - [GetAgencyAndProducersRequest](#getagencyandproducersrequest)
    - [GetAgencyAndProducersResponse](#getagencyandproducersresponse)
    - [GetAgencyFilesRequest](#getagencyfilesrequest)
    - [GetAgencyFilesResponse](#getagencyfilesresponse)
    - [GetProducerRequest](#getproducerrequest)
    - [GetProducerRequest.EmailLookup](#getproducerrequestemaillookup)
    - [GetProducerRequest.ProducerIDLookup](#getproducerrequestproduceridlookup)
    - [GetProducerRequest.ProducerNPNLookup](#getproducerrequestproducernpnlookup)
    - [GetProducerResponse](#getproducerresponse)
    - [ListNewProducersRequest](#listnewproducersrequest)
    - [ListNewProducersResponse](#listnewproducersresponse)
    - [LookupNPNByFEINRequest](#lookupnpnbyfeinrequest)
    - [LookupNPNByFEINResponse](#lookupnpnbyfeinresponse)
    - [NewAgencyRequest](#newagencyrequest)
    - [NewAgencyRequest.Agency](#newagencyrequestagency)
    - [NewAgencyRequest.Agency.BankAccount](#newagencyrequestagencybankaccount)
    - [NewAgencyRequest.Agency.BusinessHours](#newagencyrequestagencybusinesshours)
    - [NewAgencyRequest.Agency.BusinessHours.BusinessHour](#newagencyrequestagencybusinesshoursbusinesshour)
    - [NewAgencyRequest.Agency.EOInfo](#newagencyrequestagencyeoinfo)
    - [NewAgencyRequest.Agency.PointOfContact](#newagencyrequestagencypointofcontact)
    - [NewAgencyRequest.Agency.Principal](#newagencyrequestagencyprincipal)
    - [NewAgencyResponse](#newagencyresponse)
    - [NewContact](#newcontact)
    - [NewContact.Address](#newcontactaddress)
    - [NewContactRequest](#newcontactrequest)
    - [NewContactResponse](#newcontactresponse)
    - [NewContactsRequest](#newcontactsrequest)
    - [NewContactsResponse](#newcontactsresponse)
    - [NewProducer](#newproducer)
    - [NewProducer.Address](#newproduceraddress)
    - [NewProducerRequest](#newproducerrequest)
    - [NewProducerResponse](#newproducerresponse)
    - [NewProducersRequest](#newproducersrequest)
    - [NewProducersResponse](#newproducersresponse)
    - [Producer](#producer)
    - [Producer.Agency](#produceragency)
    - [Producer.NIPR](#producernipr)
    - [Producer.NIPR.Appointment](#producerniprappointment)
    - [Producer.NIPR.Biographic](#producerniprbiographic)
    - [Producer.NIPR.License](#producerniprlicense)
    - [Producer.NIPR.ProducerRegulatoryInfo](#producerniprproducerregulatoryinfo)
    - [Producer.NIPR.ProducerRegulatoryInfo.RegulatoryAction](#producerniprproducerregulatoryinforegulatoryaction)
    - [Producer.NIPR.ProducerRegulatoryInfo.RegulatoryActionsByStateEntry](#producerniprproducerregulatoryinforegulatoryactionsbystateentry)
    - [RejectProducerRequest](#rejectproducerrequest)
    - [RejectProducerResponse](#rejectproducerresponse)
    - [ResyncAgencyRequest](#resyncagencyrequest)
    - [ResyncAgencyResponse](#resyncagencyresponse)
    - [ResyncProducerRequest](#resyncproducerrequest)
    - [ResyncProducerResponse](#resyncproducerresponse)
    - [SetExternalIDRequest](#setexternalidrequest)
    - [SetExternalIDResponse](#setexternalidresponse)
    - [StopSyncAgencyWithNIPRRequest](#stopsyncagencywithniprrequest)
    - [StopSyncAgencyWithNIPRResponse](#stopsyncagencywithniprresponse)
    - [StopSyncProducerWithNIPRRequest](#stopsyncproducerwithniprrequest)
    - [StopSyncProducerWithNIPRResponse](#stopsyncproducerwithniprresponse)
    - [SyncAgencyWithNIPRRequest](#syncagencywithniprrequest)
    - [SyncAgencyWithNIPRResponse](#syncagencywithniprresponse)
    - [SyncProducerWithNIPRRequest](#syncproducerwithniprrequest)
    - [SyncProducerWithNIPRResponse](#syncproducerwithniprresponse)
    - [UpdateProducerRequest](#updateproducerrequest)
    - [UpdateProducerRequest.Producer](#updateproducerrequestproducer)
    - [UpdateProducerResponse](#updateproducerresponse)
    - [ValidateAgencyNPNRequest](#validateagencynpnrequest)
    - [ValidateAgencyNPNResponse](#validateagencynpnresponse)
    - [ValidateProducerNPNRequest](#validateproducernpnrequest)
    - [ValidateProducerNPNResponse](#validateproducernpnresponse)
  


- Enums
    - [Agency.BankAccount.AccountType](#agencybankaccountaccounttype)
    - [EntityType](#entitytype)
    - [NewAgencyRequest.Agency.BankAccount.AccountType](#newagencyrequestagencybankaccountaccounttype)
    - [NewAgencyRequest.Agency.PointOfContact.CommunicationRole](#newagencyrequestagencypointofcontactcommunicationrole)
    - [Producer.NIPR.License.LicenseStatus](#producerniprlicenselicensestatus)
    - [ProducerOnboardingState](#produceronboardingstate)
  


- [Scalar Value Types](#scalar-value-types)



# AppointmentService {#producerflowappointmentv1appointmentservice}
AppointmentService manages license appointments through NIPR.

The appointment flow in NIPR is as follows:
1. A new appointment (or termination) is requested for a license number.
2. Some time later, NIPR processes the request and returns the final result.

Since NIPR does not return results immediately, RequestAppointment and TerminateAppointment
RPCs will return a processing status of IN_PROGRESS if the request is accepted by NIPR.
When the appointment is finally processed by NIPR, ProducerFlow will notify via a webhook of
the final result. Also, any call from this point on to ListAppointments or GetAppointment will
also return the final result.

Any call to this service must be authenticated using an API key in the request headers.

## RequestAppointment

> **rpc** RequestAppointment([RequestAppointmentRequest](#requestappointmentrequest))
    [RequestAppointmentResponse](#requestappointmentresponse)

Requests a new appointment for the specified license number.
The caller must verify that the license and the producer are eligible for appointment.
If the request is accepted by NIPR, the appointment will have IN_PROGRESS processing status.
If rejected, it will have REJECTED status and reasons will be provided in not_eligible_reasons.
## GetAppointment

> **rpc** GetAppointment([GetAppointmentRequest](#getappointmentrequest))
    [GetAppointmentResponse](#getappointmentresponse)

Retrieves the details of an appointment by its ID.
## ListAppointments

> **rpc** ListAppointments([ListAppointmentsRequest](#listappointmentsrequest))
    [ListAppointmentsResponse](#listappointmentsresponse)

Lists appointments for the tenant, optionally filtered by processing status.
## TerminateAppointment

> **rpc** TerminateAppointment([TerminateAppointmentRequest](#terminateappointmentrequest))
    [TerminateAppointmentResponse](#terminateappointmentresponse)

Terminates an existing appointment by ID, providing a reason.
## CheckAppointmentEligibility

> **rpc** CheckAppointmentEligibility([CheckAppointmentEligibilityRequest](#checkappointmenteligibilityrequest))
    [CheckAppointmentEligibilityResponse](#checkappointmenteligibilityresponse)

Checks whether a license is eligible for appointment.
If not eligible, a list of reasons is provided.
## GetAppointmentFees

> **rpc** GetAppointmentFees([GetAppointmentFeesRequest](#getappointmentfeesrequest))
    [GetAppointmentFeesResponse](#getappointmentfeesresponse)

Retrieves the total fees associated with requesting an appointment. Fee amounts are represented
as integer values in cents. E.g. $10.34 is sent as 1034.
## GetTerminationFees

> **rpc** GetTerminationFees([GetTerminationFeesRequest](#getterminationfeesrequest))
    [GetTerminationFeesResponse](#getterminationfeesresponse)

Retrieves the total fees associated with terminating an appointment. Fee amounts are represented
as integer values in cents. E.g. $10.34 is sent as 1034.
 <!-- end methods -->
 <!-- end services -->

# Messages


## Appointment {#appointment}
Represents an appointment for a license.


| Field | Type | Description |
| ----- | ---- | ----------- |
| appointment_id | [ string](#string) | Unique identifier for the appointment. |
| license_number | [ string](#string) | The license number associated with the appointment. |
| appointment_type | [ AppointmentType](#appointmenttype) | Type of appointment (e.g., up-front, registry). |
| eligibility_status | [ EligibilityStatus](#eligibilitystatus) | Eligibility status of the appointment (e.g., eligible, ineligible). |
| processing_status | [ ProcessingStatus](#processingstatus) | Processing status of the appointment (e.g., in progress, appointed). |
| not_eligible_reasons | [repeated string](#string) | If ineligible or rejected, reasons will be listed here. |
| comments | [ string](#string) | Optional comments or notes related to the appointment. |
| appointment_fee_in_cents | [ int64](#int64) | Total appointment fee in cents. |
| termination_fee_in_cents | [ int64](#int64) | Total termination fee in cents, if terminated or eligible for termination. |
| created_at | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Timestamp when the appointment was created. |
| updated_at | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Timestamp of the last update to the appointment. |
 <!-- end Fields -->
 <!-- end HasFields -->


## CheckAppointmentEligibilityRequest {#checkappointmenteligibilityrequest}
Request to check appointment eligibility for a license.


| Field | Type | Description |
| ----- | ---- | ----------- |
| license_number | [ string](#string) | Required. License number to check. |
 <!-- end Fields -->
 <!-- end HasFields -->


## CheckAppointmentEligibilityResponse {#checkappointmenteligibilityresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| not_eligible_reasons | [repeated string](#string) | If not eligible, reasons will be returned. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetAppointmentFeesRequest {#getappointmentfeesrequest}
Request to get appointment fees.


| Field | Type | Description |
| ----- | ---- | ----------- |
| license_number | [ string](#string) | Required. License number to appoint. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetAppointmentFeesResponse {#getappointmentfeesresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| fee_in_cents | [ int64](#int64) | Total fee for the appointment in cents. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetAppointmentRequest {#getappointmentrequest}
Request to retrieve an appointment by ID.


| Field | Type | Description |
| ----- | ---- | ----------- |
| appointment_id | [ string](#string) | Required. The ID of the appointment to retrieve. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetAppointmentResponse {#getappointmentresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| appointment | [ Appointment](#appointment) | The appointment details. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetTerminationFeesRequest {#getterminationfeesrequest}
Request to get termination fees.


| Field | Type | Description |
| ----- | ---- | ----------- |
| appointment_id | [ string](#string) | Required. Appointment ID. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetTerminationFeesResponse {#getterminationfeesresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| fee_in_cents | [ int64](#int64) | Total fee for the termination in cents. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ListAppointmentsRequest {#listappointmentsrequest}
Request to list appointments, optionally filtered by processing status.


| Field | Type | Description |
| ----- | ---- | ----------- |
| processing_status | [repeated ProcessingStatus](#processingstatus) | Optional. Filter results by processing status. |
| page_size | [ int32](#int32) | Optional. Maximum number of results to return. |
| page_token | [ string](#string) | Optional. Token for fetching the next page. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ListAppointmentsResponse {#listappointmentsresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| appointments | [repeated Appointment](#appointment) | List of appointments. |
| next_page_token | [ string](#string) | Token for fetching the next page of results. |
 <!-- end Fields -->
 <!-- end HasFields -->


## RequestAppointmentRequest {#requestappointmentrequest}
Request to create a new appointment.


| Field | Type | Description |
| ----- | ---- | ----------- |
| license_number | [ string](#string) | Required. License number to appoint. |
 <!-- end Fields -->
 <!-- end HasFields -->


## RequestAppointmentResponse {#requestappointmentresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| appointment_id | [ string](#string) | The ID of the created appointment. |
| processing_status | [ ProcessingStatus](#processingstatus) | Processing status of the appointment request. |
| not_eligible_reasons | [repeated string](#string) | If the appointment was rejected or ineligible, these reasons explain why. |
 <!-- end Fields -->
 <!-- end HasFields -->


## TerminateAppointmentRequest {#terminateappointmentrequest}
Request to terminate an appointment.


| Field | Type | Description |
| ----- | ---- | ----------- |
| appointment_id | [ string](#string) | Required. ID of the appointment to terminate. |
| reason | [ string](#string) | Required. Reason for termination. |
 <!-- end Fields -->
 <!-- end HasFields -->


## TerminateAppointmentResponse {#terminateappointmentresponse}



| Field | Type | Description |
| ----- | ---- | ----------- |
| success | [ bool](#bool) | Indicates whether the termination was successful. |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums


## AppointmentType {#appointmenttype}
Type of appointment.

| Name | Number | Description |
| ---- | ------ | ----------- |
| APPOINTMENT_TYPE_UNSPECIFIED | 0 | none |
| APPOINTMENT_TYPE_REGISTRY | 1 | none |
| APPOINTMENT_TYPE_UP_FRONT | 2 | none |
| APPOINTMENT_TYPE_JUST_IN_TIME | 3 | none |




## EligibilityStatus {#eligibilitystatus}
Eligibility status of the appointment.

| Name | Number | Description |
| ---- | ------ | ----------- |
| ELIGIBILITY_STATUS_UNSPECIFIED | 0 | none |
| ELIGIBILITY_STATUS_ELIGIBLE | 1 | none |
| ELIGIBILITY_STATUS_INELIGIBLE | 2 | none |




## ProcessingStatus {#processingstatus}
Processing status of the appointment.

| Name | Number | Description |
| ---- | ------ | ----------- |
| PROCESSING_STATUS_UNSPECIFIED | 0 | none |
| PROCESSING_STATUS_IN_PROGRESS | 1 | none |
| PROCESSING_STATUS_APPOINTED | 2 | none |
| PROCESSING_STATUS_TERMINATED | 3 | none |
| PROCESSING_STATUS_REJECTED | 4 | none |
| PROCESSING_STATUS_MISSING_LICENSE | 5 | none |


 <!-- end Enums -->


# ProducerService {#producerflowproducerv1producerservice}
ProducerService provides a comprehensive API for managing insurance producers
and agencies, including onboarding, data synchronization, and integration with
external systems like NIPR for license verification.

RPCs for starting the onboarding agency process.

## CreateAgencyOnboardingURL

> **rpc** CreateAgencyOnboardingURL([CreateAgencyOnboardingURLRequest](#createagencyonboardingurlrequest))
    [CreateAgencyOnboardingURLResponse](#createagencyonboardingurlresponse)

CreateAgencyOnboardingURL generates a URL that can be used to onboard a new agency.
The URL contains encoded information about the agency defaults and tenant context.
Returns a URL string that can be shared with the agency for self-onboarding.
## NewAgency

> **rpc** NewAgency([NewAgencyRequest](#newagencyrequest))
    [NewAgencyResponse](#newagencyresponse)

NewAgency creates a new agency, optionally with associated producers.
It performs the following validation checks:
- Ensures all required fields are present and valid
- Checks whether the NPN is already registered
- Verifies agency and principal information with NIPR

Business rules:
- Sole proprietors can't have an agency NPN or additional producers
- Regular agencies must provide either an NPN or a FEIN

If validation passes, it creates the agency, principal, and any producers.
Returns the IDs of the created agency, principal, and producers.
## NewProducer

> **rpc** NewProducer([NewProducerRequest](#newproducerrequest))
    [NewProducerResponse](#newproducerresponse)

NewProducer creates a new producer and associates them with an existing agency.
It validates the producer's information and checks that the email is unique.
Returns the ID of the created producer.
## NewProducers

> **rpc** NewProducers([NewProducersRequest](#newproducersrequest))
    [NewProducersResponse](#newproducersresponse)

NewProducers creates multiple producers and associates them with the specified agency.
It performs the same validations as NewProducer for each entry.
Returns the IDs of all created producers.
## GetAgencyAndProducers

> **rpc** GetAgencyAndProducers([GetAgencyAndProducersRequest](#getagencyandproducersrequest))
    [GetAgencyAndProducersResponse](#getagencyandproducersresponse)

GetAgencyAndProducers retrieves details for an agency and all associated producers.
Returns the agency information and a list of producers.
## GetProducer

> **rpc** GetProducer([GetProducerRequest](#getproducerrequest))
    [GetProducerResponse](#getproducerresponse)

GetProducer retrieves detailed information about a specific producer.
The producer can be found by ID, NPN, or email.
Returns the producer's information, including NIPR data and agency association.
## GetAgencyFiles

> **rpc** GetAgencyFiles([GetAgencyFilesRequest](#getagencyfilesrequest))
    [GetAgencyFilesResponse](#getagencyfilesresponse)

GetAgencyFiles returns URLs for accessing files associated with an agency, such as contracts.
## UpdateProducer

> **rpc** UpdateProducer([UpdateProducerRequest](#updateproducerrequest))
    [UpdateProducerResponse](#updateproducerresponse)

UpdateProducer updates information for an existing producer.
Supports updating contact details, background check responses,
employment history, and non-uniform licensing questions.
Information from NIPR and other third-party sources cannot be updated.
Validates email uniqueness if the email is changed.
## ApproveProducer

> **rpc** ApproveProducer([ApproveProducerRequest](#approveproducerrequest))
    [ApproveProducerResponse](#approveproducerresponse)

ApproveProducer changes a producer's onboarding state to APPROVED.
This typically happens after all verification steps are complete.
This method is deprecated. Use SyncProducerWithNIPR instead.
## RejectProducer

> **rpc** RejectProducer([RejectProducerRequest](#rejectproducerrequest))
    [RejectProducerResponse](#rejectproducerresponse)

RejectProducer changes a producer's onboarding state to REJECTED.
An optional reason for rejection can be provided.
This method is deprecated. Use StopSyncAgencyWithNIPR instead.
## NewContact

> **rpc** NewContact([NewContactRequest](#newcontactrequest))
    [NewContactResponse](#newcontactresponse)

NewContact creates a new contact associated with an agency.
Contacts represent non-producer individuals linked to the agency.
Returns the ID of the created contact.
## NewContacts

> **rpc** NewContacts([NewContactsRequest](#newcontactsrequest))
    [NewContactsResponse](#newcontactsresponse)

NewContacts creates multiple contacts in a single request.
Each contact is associated with the specified agency.
Returns the IDs of all created contacts.
## SetExternalID

> **rpc** SetExternalID([SetExternalIDRequest](#setexternalidrequest))
    [SetExternalIDResponse](#setexternalidresponse)

SetExternalID sets an external identifier for a producer or contact.
Useful for integrating with external systems that use different ID schemes.
## ValidateProducerNPN

> **rpc** ValidateProducerNPN([ValidateProducerNPNRequest](#validateproducernpnrequest))
    [ValidateProducerNPNResponse](#validateproducernpnresponse)

ValidateProducerNPN checks whether a producer’s National Producer Number (NPN) is valid.
It performs a lookup against NIPR and applies internal validation rules.
Returns a validity flag and any associated error messages.
## ValidateAgencyNPN

> **rpc** ValidateAgencyNPN([ValidateAgencyNPNRequest](#validateagencynpnrequest))
    [ValidateAgencyNPNResponse](#validateagencynpnresponse)

ValidateAgencyNPN checks whether an agency’s National Producer Number (NPN) is valid.
It performs a lookup against NIPR and applies internal validation rules.
Returns a validity flag and any associated error messages.
## LookupNPNByFEIN

> **rpc** LookupNPNByFEIN([LookupNPNByFEINRequest](#lookupnpnbyfeinrequest))
    [LookupNPNByFEINResponse](#lookupnpnbyfeinresponse)

LookupNPNByFEIN finds an NPN using a Federal Employer Identification Number.
Used to help agencies that know their FEIN but not their NPN.
Returns the NPN if found or an error message.
## ResyncProducer

> **rpc** ResyncProducer([ResyncProducerRequest](#resyncproducerrequest))
    [ResyncProducerResponse](#resyncproducerresponse)

ResyncProducer triggers a manual resynchronization of a producer’s data.
This can be used to refresh data after external changes.

WARNING: This call counts as an additional NPN lookup for billing purposes.
Most billing plans are based on unique NPNs per month, so using this
method may result in extra charges.
## ResyncAgency

> **rpc** ResyncAgency([ResyncAgencyRequest](#resyncagencyrequest))
    [ResyncAgencyResponse](#resyncagencyresponse)

ResyncAgency triggers a manual resynchronization of an agency’s data.
Similar to ResyncProducer, this can be used to refresh data after external changes.

WARNING: This call counts as an additional NPN lookup for billing purposes.
Most billing plans are based on unique NPNs per month, so using this
method may result in extra charges.
## SyncProducerWithNIPR

> **rpc** SyncProducerWithNIPR([SyncProducerWithNIPRRequest](#syncproducerwithniprrequest))
    [SyncProducerWithNIPRResponse](#syncproducerwithniprresponse)

SyncAgencyWithNIPR synchronizes an producer’s data with the NIPR system.
Fetches the latest producer information and appointments.

WARNING: This call counts as an extra NPN lookup against your billing.
Most billing plans are based on unique NPNs per month, so using this
method may result in additional charges.
## SyncAgencyWithNIPR

> **rpc** SyncAgencyWithNIPR([SyncAgencyWithNIPRRequest](#syncagencywithniprrequest))
    [SyncAgencyWithNIPRResponse](#syncagencywithniprresponse)

SyncAgencyWithNIPR synchronizes an agency’s data with the NIPR system.
Fetches the latest agency information and appointments.

WARNING: This call counts as an extra NPN lookup against your billing.
Most billing plans are based on unique NPNs per month, so using this
method may result in additional charges.
## StopSyncProducerWithNIPR

> **rpc** StopSyncProducerWithNIPR([StopSyncProducerWithNIPRRequest](#stopsyncproducerwithniprrequest))
    [StopSyncProducerWithNIPRResponse](#stopsyncproducerwithniprresponse)

StopSyncProducerWithNIPR stops the synchronization process with NIPR for a producer.
Use this to prevent further automatic updates from NIPR.
## StopSyncAgencyWithNIPR

> **rpc** StopSyncAgencyWithNIPR([StopSyncAgencyWithNIPRRequest](#stopsyncagencywithniprrequest))
    [StopSyncAgencyWithNIPRResponse](#stopsyncagencywithniprresponse)

StopSyncAgencyWithNIPR stops the synchronization process with NIPR for an agency.
Use this to prevent further automatic updates from NIPR.
 <!-- end methods -->
 <!-- end services -->

# Messages


## Address {#address}
Address represents a physical location with standard address components.
Used for mailing, physical, and invoicing addresses throughout the API.


| Field | Type | Description |
| ----- | ---- | ----------- |
| street | [ string](#string) | Street address including house/building number and street name |
| city | [ string](#string) | City of the address |
| state | [ string](#string) | State of the address |
| zip | [ string](#string) | Zip code of the address |
| county | [ string](#string) | County of the address |
 <!-- end Fields -->
 <!-- end HasFields -->


## Agency {#agency}
Agency represents a complete agency entity with all associated information.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | Unique identifier for the agency. |
| agency_info | [ Agency.AgencyInfo](#agencyagencyinfo) | AgencyInfo type field named agency_info |
| address | [ Agency.Address](#agencyaddress) | Address type field named address. |
| mailing_address | [ Agency.Address](#agencyaddress) | Address type field named mailing_address. |
| bank_account | [ Agency.BankAccount](#agencybankaccount) | Banking information for commission payments. Used for electronic transfers of commissions and other payments. |
| eo_info | [ Agency.EOInfo](#agencyeoinfo) | none |
| principal | [ Agency.Principal](#agencyprincipal) | Information about the agency's principal. This is a required field as each agency must have a principal. |
| ivans_account | [ Agency.IvansAccount](#agencyivansaccount) | IVANS account information for electronic carrier communication. This is optional and only used if the agency uses IVANS. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Agency.Address {#agencyaddress}
Address is a data structure that represents a physical or mailing
location.


| Field | Type | Description |
| ----- | ---- | ----------- |
| street | [ string](#string) | Street name and number of the location. |
| city | [ string](#string) | City where the location resides. |
| state | [ string](#string) | State/Province where the location resides. |
| zip | [ string](#string) | ZIP/Postal code of the location. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Agency.AgencyInfo {#agencyagencyinfo}
AgencyInfo contains contact and identification information for an agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| onboarding_id | [ string](#string) | The unique identifier for the onboarding process. Used to track the agency through the onboarding flow. |
| root_organization_id | [ string](#string) | The organization ID represents the ID of the root organization that the agency belongs to. An example of a root organization is an Aggregator (Like AgencyHero) or an Agency Network. We currently don't support multiple levels of organizations or agencies. Agencies are not always part of an organization, so this field is optional. |
| agency_name | [ string](#string) | The official name of the agency. This is typically the legal name of the entity. |
| agency_fein | [ string](#string) | Federal Employer Identification Number (FEIN) of the agency. This is a unique nine-digit number assigned by the Internal Revenue Service (IRS) to businesses operating in the United States. |
| email | [ string](#string) | Primary email address for the agency. Used for communication and must be unique. |
| phone | [ string](#string) | Phone number for the agency. |
| fax | [ string](#string) | Fax number for the agency. |
| website | [ string](#string) | Website URL for the agency, if available. |
| npn | [ string](#string) | National Producer Number (NPN) of the agency. This is a unique identifier assigned by the National Association of Insurance Commissioners (NAIC). |
| pdb_alerts_sync_enabled | [ bool](#bool) | Indicates whether the agency is enabled to be synchronized with NIPR API. When true, the system will regularly check for updates from NIPR. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Agency.BankAccount {#agencybankaccount}
BankAccount contains information about a bank account for commission payments.


| Field | Type | Description |
| ----- | ---- | ----------- |
| account_number | [ string](#string) | Account number for the bank account. |
| routing_number | [ string](#string) | Routing number for the bank. This is a nine-digit code identifying the financial institution. |
| account_type | [ Agency.BankAccount.AccountType](#agencybankaccountaccounttype) | Type of account (checking or savings). Indicates how the account should be treated for electronic transfers. |
| account_holder_name | [ string](#string) | Name of the account holder as it appears on bank records. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Agency.EOInfo {#agencyeoinfo}
EOInfo contains Errors & Omissions insurance information


| Field | Type | Description |
| ----- | ---- | ----------- |
| carrier | [ string](#string) | Insurance carrier providing the E&O coverage |
| expiration_date | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Date when the E&O coverage will expire |
| coverage_amount | [ string](#string) | Amount of coverage provided by the E&O policy |
 <!-- end Fields -->
 <!-- end HasFields -->


## Agency.IvansAccount {#agencyivansaccount}
IvansAccount contains information for IVANS integration.
IVANS is a system for electronic communication between insurance agencies and carriers.


| Field | Type | Description |
| ----- | ---- | ----------- |
| account_number | [ string](#string) | Account number for the IVANS service. |
| ams_software | [ string](#string) | Software used for IVANS communication. |
| ams_version | [ string](#string) | Version of the IVANS software. |
| mailbox_number | [ string](#string) | Mailbox number for the IVANS service. Used for routing electronic messages. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Agency.Principal {#agencyprincipal}
Principal is a data structure that represents the principal of a agency.
A principal is the person or entity that is responsible for the day-to-day operations of the agency.
The principal is usually the CEO or CFO of the agency.nThe principal is also known as the "owner" of the agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | Unique identifier for the principal (as a producer). |
| first_name | [ string](#string) | First name of the principal. |
| last_name | [ string](#string) | Last name of the principal. |
| middle_name | [ string](#string) | Middle name of the principal. |
| email | [ string](#string) | Email address of the principal. Must be unique and is used for communication. |
| npn | [ string](#string) | The NPN of the principal. This is used to retrieve the license information of the principal from the NIPR API. |
| phone | [ string](#string) | Phone number of the principal. Used for communication. |
| mailing_address | [ Agency.Address](#agencyaddress) | Mailing address of the principal. This may differ from the agency address. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ApproveProducerRequest {#approveproducerrequest}
ApproveProducerRequest requests approval for a producer in the onboarding process.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_id | [ string](#string) | The UUID of the producer to approve. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ApproveProducerResponse {#approveproducerresponse}
ApproveProducerResponse is the empty response returned after successfully approving a producer.

 <!-- end HasFields -->


## CreateAgencyOnboardingURLRequest {#createagencyonboardingurlrequest}
CreateAgencyOnboardingURLRequest contains information needed to generate
an agency onboarding URL. This includes basic agency information and defaults.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency | [ CreateAgencyOnboardingURLRequest.Agency](#createagencyonboardingurlrequestagency) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateAgencyOnboardingURLRequest.Agency {#createagencyonboardingurlrequestagency}
Agency contains the information about the agency to be onboarded


| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | Name of the agency |
| entity_type | [ EntityType](#entitytype) | Entity type of the agency: Sole Proprietor, Agency or Ask during onboarding |
| tenant_agency_id | [ string](#string) | Tenant agency id is a unique identifier for the agency used by the tenant this is used to identify the agency in the tenant system not in the producerflow system |
| docusign_template_id | [ string](#string) | DocuSign template id is the id of the docusign template used to send the contract to the agency |
| fein | [ string](#string) | FEIN (Federal Employer Identification Number) of the agency |
| email | [ string](#string) | Email of the agency |
| phone | [ string](#string) | Phone of the agency |
| fax | [ string](#string) | Fax of the agency |
| website | [ string](#string) | Website of the agency |
| npn | [ string](#string) | NPN of the agency. Note that if the entity type is Sole Proprietor the NPN will be ignored |
| mailing_address | [ Address](#address) | Mailing address of the agency |
| physical_address | [ Address](#address) | Physical address of the agency |
| invoicing_address | [ Address](#address) | Invoicing address of the agency |
| principal | [ CreateAgencyOnboardingURLRequest.Agency.Principal](#createagencyonboardingurlrequestagencyprincipal) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateAgencyOnboardingURLRequest.Agency.Principal {#createagencyonboardingurlrequestagencyprincipal}
Principal is the person responsible for the agency


| Field | Type | Description |
| ----- | ---- | ----------- |
| tenant_id | [ string](#string) | Tenant ID of the principal |
| first_name | [ string](#string) | First name of the principal |
| last_name | [ string](#string) | Last name of the principal |
| middle_name | [ string](#string) | Middle name of the principal |
| email | [ string](#string) | Email of the principal |
| phone | [ string](#string) | Phone of the principal |
| npn | [ string](#string) | NPN of the principal |
| address | [ Address](#address) | Address of the principal |
 <!-- end Fields -->
 <!-- end HasFields -->


## CreateAgencyOnboardingURLResponse {#createagencyonboardingurlresponse}
CreateAgencyOnboardingURLResponse contains the generated URL for agency onboarding


| Field | Type | Description |
| ----- | ---- | ----------- |
| url | [ string](#string) | URL that can be shared with the agency for self-onboarding |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetAgencyAndProducersRequest {#getagencyandproducersrequest}
GetAgencyAndProducersRequest requests information about an agency and all associated producers.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to retrieve information for. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetAgencyAndProducersResponse {#getagencyandproducersresponse}
GetAgencyAndProducersResponse contains the agency information and all associated producers.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency | [ Agency](#agency) | Complete agency information including contact details, principal, and bank account. |
| producers | [repeated Producer](#producer) | List of all producers associated with the specified agency. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetAgencyFilesRequest {#getagencyfilesrequest}
GetAgencyFilesRequest requests URLs for files associated with an agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to retrieve files for. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetAgencyFilesResponse {#getagencyfilesresponse}
GetAgencyFilesResponse contains URLs for various documents associated with an agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| eo_doc_url | [ string](#string) | URL of the Errors & Omissions (E&O) insurance document. |
| voided_check_doc_url | [ string](#string) | URL of the bank voided check document. It's used to safely share bank account information for electronic transfers. |
| w9_doc_url | [ string](#string) | URL of the W9 form document. It's a U.S. internal revenue service form, an identification document used in the onboarding process for tax reporting purposes. |
| license_doc_url | [ string](#string) | URL of the license document. An identification document that shows that the agency is licensed to carry out its operations in the relevant jurisdictions. |
| broker_bond_doc_url | [ string](#string) | URL of the broker bond document. It's a surety bond that a broker needs to operate legally, providing financial security for clients. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetProducerRequest {#getproducerrequest}
GetProducerRequest allows retrieving producer information through one of three
possible lookup methods: by ID, by NPN, or by email address.


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) lookup_method.producer_id_lookup | [ GetProducerRequest.ProducerIDLookup](#getproducerrequestproduceridlookup) | Look up producer by ID. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) lookup_method.npn_lookup | [ GetProducerRequest.ProducerNPNLookup](#getproducerrequestproducernpnlookup) | Look up producer by NPN. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) lookup_method.email_lookup | [ GetProducerRequest.EmailLookup](#getproducerrequestemaillookup) | Look up producer by email. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetProducerRequest.EmailLookup {#getproducerrequestemaillookup}
EmailLookup allows looking up a producer by their email address.


| Field | Type | Description |
| ----- | ---- | ----------- |
| email | [ string](#string) | The email address of the producer to retrieve. Must be a valid email format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetProducerRequest.ProducerIDLookup {#getproducerrequestproduceridlookup}
ProducerIDLookup allows looking up a producer by their unique identifier.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_id | [ string](#string) | The UUID of the producer to retrieve. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetProducerRequest.ProducerNPNLookup {#getproducerrequestproducernpnlookup}
ProducerNPNLookup allows looking up a producer by their National Producer Number (NPN).


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_npn | [ string](#string) | The National Producer Number (NPN) of the producer to retrieve. Must be a non-empty string. |
 <!-- end Fields -->
 <!-- end HasFields -->


## GetProducerResponse {#getproducerresponse}
GetProducerResponse contains the producer information retrieved by the GetProducer RPC.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer | [ Producer](#producer) | The complete producer information including personal details, agency association, and NIPR data. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ListNewProducersRequest {#listnewproducersrequest}
ListNewProducersRequest requests a list of new producers, optionally filtered by agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _agency_id.agency_id | [optional string](#string) | Optional agency ID to filter producers by. If provided, only producers belonging to this agency will be returned. If not provided, producers from all agencies will be returned. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ListNewProducersResponse {#listnewproducersresponse}
ListNewProducersResponse contains a list of new producers that match the filter criteria.


| Field | Type | Description |
| ----- | ---- | ----------- |
| new_producers | [repeated Producer](#producer) | List of new producers matching the filter criteria. These are producers typically in the NEW or pending onboarding state. |
 <!-- end Fields -->
 <!-- end HasFields -->


## LookupNPNByFEINRequest {#lookupnpnbyfeinrequest}
LookupNPNByFEINRequest is used to look up a producer's National Producer Number by their Federal Employer Identification Number (FEIN).


| Field | Type | Description |
| ----- | ---- | ----------- |
| fein | [ string](#string) | The Federal Employer Identification Number (FEIN) to look up. Required and must be exactly 9 characters. |
 <!-- end Fields -->
 <!-- end HasFields -->


## LookupNPNByFEINResponse {#lookupnpnbyfeinresponse}
LookupNPNByFEINResponse contains the National Producer Number (NPN) for the producer associated with the given FEIN.


| Field | Type | Description |
| ----- | ---- | ----------- |
| npn | [ string](#string) | The National Producer Number (NPN) for the producer. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyRequest {#newagencyrequest}
NewAgencyRequest contains complete information for creating a new agency


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency | [ NewAgencyRequest.Agency](#newagencyrequestagency) | none |
| auto_approve | [ bool](#bool) | Determines if the agency should be auto approved. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyRequest.Agency {#newagencyrequestagency}
Agency contains all information about the agency to be created


| Field | Type | Description |
| ----- | ---- | ----------- |
| name | [ string](#string) | The name of the agency. |
| email | [ string](#string) | The email address of the agency. |
| npn | [ string](#string) | National Producer Number for the agency Required for ENTITY_TYPE_AGENCY if FEIN is not provided Not allowed for ENTITY_TYPE_SOLE_PROPRIETOR |
| phone | [ string](#string) | The phone number of the agency. |
| website | [ string](#string) | The website of the agency. |
| principal | [ NewAgencyRequest.Agency.Principal](#newagencyrequestagencyprincipal) | Information about the agency's principal. This is a required field as each agency must have a principal. |
| bank_account | [ NewAgencyRequest.Agency.BankAccount](#newagencyrequestagencybankaccount) | none |
| eo_info | [ NewAgencyRequest.Agency.EOInfo](#newagencyrequestagencyeoinfo) | none |
| business_hours | [ NewAgencyRequest.Agency.BusinessHours](#newagencyrequestagencybusinesshours) | none |
| producers | [repeated NewProducer](#newproducer) | List of producers associated with the agency |
| points_of_contact | [repeated NewAgencyRequest.Agency.PointOfContact](#newagencyrequestagencypointofcontact) | none |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _root_organization_id.root_organization_id | [optional string](#string) | RootOrganizationID represents the ID of the root organization that the agency belongs to. An example of a root organization is an Aggregator (Like AgencyHero) or an Agency Network. We currently don't support multiple levels of organizations or agencies. Agencies are not always part of an organization, so this field is optional. |
| entity_type | [ EntityType](#entitytype) | EntityType represents the type of business entity for an agency. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _fein.fein | [optional string](#string) | FEIN represents the Federal Employer Identification Number of the agency. Required for ENTITY_TYPE_AGENCY Not allowed for ENTITY_TYPE_SOLE_PROPRIETOR |
| mailing_address | [ Address](#address) | MailingAddress represents the mailing address of the agency. |
| physical_address | [ Address](#address) | PhysicalAddress represents the physical address of the agency. |
| invoicing_address | [ Address](#address) | InvoicingAddress represents the invoicing address of the agency. |
| tenant_agency_id | [ string](#string) | TenantAgencyID represents the ID of the agency in the tenant. This is used to link the agency to the tenant. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyRequest.Agency.BankAccount {#newagencyrequestagencybankaccount}
BankAccount contains banking information for commission payments
This is used to store the bank account information for the agency


| Field | Type | Description |
| ----- | ---- | ----------- |
| account_number | [ string](#string) | none |
| routing_number | [ string](#string) | Routing number for the bank account |
| account_type | [ NewAgencyRequest.Agency.BankAccount.AccountType](#newagencyrequestagencybankaccountaccounttype) | Type of account (checking or savings) |
| account_holder_name | [ string](#string) | Name of the account holder |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyRequest.Agency.BusinessHours {#newagencyrequestagencybusinesshours}
BusinessHours contains the business hours of the agency


| Field | Type | Description |
| ----- | ---- | ----------- |
| timezone | [ string](#string) | Timezone of the agency |
| business_hours | [repeated NewAgencyRequest.Agency.BusinessHours.BusinessHour](#newagencyrequestagencybusinesshoursbusinesshour) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyRequest.Agency.BusinessHours.BusinessHour {#newagencyrequestagencybusinesshoursbusinesshour}



| Field | Type | Description |
| ----- | ---- | ----------- |
| week_days | [repeated google.type.DayOfWeek](#googletypedayofweek) | Days of the week when the agency is open |
| opening_time | [ google.type.TimeOfDay](#googletypetimeofday) | Time when the agency opens |
| closing_time | [ google.type.TimeOfDay](#googletypetimeofday) | Time when the agency closes |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyRequest.Agency.EOInfo {#newagencyrequestagencyeoinfo}
EOInfo contains Errors & Omissions insurance information


| Field | Type | Description |
| ----- | ---- | ----------- |
| carrier | [ string](#string) | Insurance carrier providing the E&O coverage |
| expiration_date | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Date when the E&O coverage will expire |
| coverage_amount | [ string](#string) | Amount of coverage provided by the E&O policy |
| effective_date | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Date when the E&O coverage will become effective |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyRequest.Agency.PointOfContact {#newagencyrequestagencypointofcontact}
PointOfContact contains contact information for the agency. Each point of contact
consists of an email address with an associated role. Carriers will send specific
information to these email addresses based on their roles. For example, if an email
is assigned the COMMUNICATION_ROLE_ACCOUNTING role, all accounting information from
the carrier will be sent to that email address.


| Field | Type | Description |
| ----- | ---- | ----------- |
| email | [ string](#string) | Email address of the point of contact |
| role | [ NewAgencyRequest.Agency.PointOfContact.CommunicationRole](#newagencyrequestagencypointofcontactcommunicationrole) | Role of the point of contact |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyRequest.Agency.Principal {#newagencyrequestagencyprincipal}
Principal is a data structure that represents the principal of a agency.
A principal is the person or entity that is responsible for the day-to-day operations of the agency.
The principal is usually the CEO or CFO of the agency.nThe principal is also known as the "owner" of the agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| first_name | [ string](#string) | The first name of the principal. |
| last_name | [ string](#string) | The last name of the principal. |
| middle_name | [ string](#string) | The middle name of the principal. |
| email | [ string](#string) | The email address of the principal. |
| phone | [ string](#string) | The phone number of the principal. |
| npn | [ string](#string) | The National Producer Number (NPN) of the principal. |
| tenant_id | [ string](#string) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewAgencyResponse {#newagencyresponse}
NewAgencyResponse contains the IDs of created resources after a successful agency creation


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | Unique identifier for the created agency |
| producer_ids | [repeated string](#string) | List of unique identifiers for any producers created with the agency |
| principal_id | [ string](#string) | Unique identifier for the principal producer |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewContact {#newcontact}
NewContact represents the data needed to create a new contact in the system.
Contacts represent non-producer individuals associated with an agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| first_name | [ string](#string) | First name of the contact. Required and must be non-empty. |
| last_name | [ string](#string) | Last name of the contact. Required and must be non-empty. |
| middle_name | [ string](#string) | Middle name of the contact. Optional. |
| email | [ string](#string) | Email address of the contact. Required and must be a valid email format. Must be unique within the tenant. |
| phone | [ string](#string) | Phone number of the contact. Optional if default value, but if provided must match the pattern of a valid phone number. |
| address | [ NewContact.Address](#newcontactaddress) | Mailing address of the contact. |
| role | [ string](#string) | Role or position of the contact within the agency. Required and must be non-empty. |
| tenant_id | [ string](#string) | External tenant identifier for the contact. Used for integration with external systems. |
| npn | [ string](#string) | National Producer Number (NPN) of the contact. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewContact.Address {#newcontactaddress}
Address represents a mailing address for the contact.


| Field | Type | Description |
| ----- | ---- | ----------- |
| street | [ string](#string) | Street address of the contact. Required and must be non-empty. |
| city | [ string](#string) | City of the contact. Required and must be non-empty. |
| state | [ string](#string) | State of the contact's address. Required and must be exactly 2 characters (state code). |
| zip | [ string](#string) | Zip code of the contact's address. Required and must be between 1 and 10 characters. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewContactRequest {#newcontactrequest}
NewContactRequest is used to create a new contact and associate it with an agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to associate the contact with. Must be a valid UUID format. |
| contact | [ NewContact](#newcontact) | Information about the contact to create. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewContactResponse {#newcontactresponse}
NewContactResponse contains the ID of the created contact.


| Field | Type | Description |
| ----- | ---- | ----------- |
| contact_id | [ string](#string) | The UUID of the created contact. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewContactsRequest {#newcontactsrequest}
NewContactsRequest is used to create multiple contacts in a single request.
All contacts will be associated with the specified agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to associate the contacts with. Must be a valid UUID format. |
| contacts | [repeated NewContact](#newcontact) | List of contacts to create. This field is required and must contain at least one contact. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewContactsResponse {#newcontactsresponse}
NewContactsResponse contains the IDs of all created contacts.


| Field | Type | Description |
| ----- | ---- | ----------- |
| contact_ids | [repeated string](#string) | List of UUIDs for the newly created contacts. The order matches the order of contacts in the request. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewProducer {#newproducer}
NewProducer represents the data needed to create a new producer in the system.


| Field | Type | Description |
| ----- | ---- | ----------- |
| first_name | [ string](#string) | First name of the producer. Required and must be non-empty. |
| last_name | [ string](#string) | Last name of the producer. Required and must be non-empty. |
| middle_name | [ string](#string) | Middle name of the producer. Optional. |
| email | [ string](#string) | Email address of the producer. Required and must be a valid email format. Must be unique within the tenant. |
| npn | [ string](#string) | National Producer Number (NPN) of the producer. Optional, but recommended for license verification. |
| phone | [ string](#string) | Phone number of the producer. Optional if default value, but if provided must match the pattern of a valid phone number. |
| mailing_address | [ NewProducer.Address](#newproduceraddress) | Mailing address of the producer. This is where correspondence will be sent. |
| tenant_id | [ string](#string) | External tenant identifier for the producer. Used for integration with external systems. |
| auto_approve | [ bool](#bool) | Indicates whether the producer should be automatically approved. This field is deprecated and should not be used in new code. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewProducer.Address {#newproduceraddress}
Address represents a mailing address for the producer.


| Field | Type | Description |
| ----- | ---- | ----------- |
| street | [ string](#string) | Street address of the producer. Required and must be non-empty. |
| city | [ string](#string) | City of the producer. Required and must be non-empty. |
| state | [ string](#string) | State of the producer. Required and must be a 2-letter state code. |
| zip | [ string](#string) | Zip code of the producer. Required and must be between 1 and 10 characters. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewProducerRequest {#newproducerrequest}
NewProducerRequest is used to create a new producer and associate it with an agency.
This will trigger a call to the NIPR API to retrieve license information of the producer.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to associate the producer with. Must be a valid UUID format. |
| producer | [ NewProducer](#newproducer) | Information about the producer to create. This field is required. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewProducerResponse {#newproducerresponse}
NewProducerResponse contains the ID of the created producer.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_id | [ string](#string) | The UUID of the created producer. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewProducersRequest {#newproducersrequest}
NewProducersRequest is used to create multiple producers in a single request.
All producers will be associated with the specified agency.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to associate the producers with. Must be a valid UUID format. |
| producers | [repeated NewProducer](#newproducer) | List of producers to create. This field is required and must contain at least one producer. |
 <!-- end Fields -->
 <!-- end HasFields -->


## NewProducersResponse {#newproducersresponse}
NewProducersResponse contains the IDs of all created producers.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_ids | [repeated string](#string) | List of UUIDs for the newly created producers. The order matches the order of producers in the request. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer {#producer}
Producer represents a producer that has been onboarded.

Internal ID of the producer.


| Field | Type | Description |
| ----- | ---- | ----------- |
| id | [ string](#string) | The full name of the producer. |
| name | [ string](#string) | none |
| email | [ string](#string) | The email address of the producer. Used for communication and must be unique within the tenant. Must be a valid email format. |
| npn | [ string](#string) | The National Producer Number (NPN) of the producer. This is used to retrieve license information from the NIPR API. Must be non-empty. |
| pdb_alerts_sync_enabled | [ bool](#bool) | Indicates whether the producer is enabled to be synchronized with NIPR API. When true, the system will regularly check for updates from NIPR. |
| agency | [ Producer.Agency](#produceragency) | Basic information about the agency this producer is associated with. |
| nipr | [ Producer.NIPR](#producernipr) | Data synchronized from the NIPR service. Contains license information, biographic data, regulatory actions, and carrier appointments. |
| onboarding_status | [ ProducerOnboardingState](#produceronboardingstate) | The status of the producer onboarding process. This field is deprecated and should not be used in new code. |
| is_principal | [ bool](#bool) | Indicates whether this producer is the principal of an agency. A principal producer has additional responsibilities and permissions. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer.Agency {#produceragency}
Agency contains basic information about the agency this producer is associated with.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | Unique identifier for the associated agency. |
| name | [ string](#string) | Name of the associated agency. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer.NIPR {#producernipr}
NIPR contains data synchronized from the National Insurance Producer Registry.


| Field | Type | Description |
| ----- | ---- | ----------- |
| licenses | [repeated Producer.NIPR.License](#producerniprlicense) | List of all licenses held by the producer across different states. |
| biographic | [ Producer.NIPR.Biographic](#producerniprbiographic) | Biographic information of the producer from NIPR |
| regulatory_info | [ Producer.NIPR.ProducerRegulatoryInfo](#producerniprproducerregulatoryinfo) | Producer's regulatory information from NIPR |
| appointments | [repeated Producer.NIPR.Appointment](#producerniprappointment) | List of carrier appointments held by the producer in NIPR. These represent relationships with insurance carriers that allow the producer to sell their products. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer.NIPR.Appointment {#producerniprappointment}
Appointment represents a relationship between a producer and an insurance carrier.


| Field | Type | Description |
| ----- | ---- | ----------- |
| branch_id | [ string](#string) | none |
| company_name | [ string](#string) | Name of the insurance company for this appointment. |
| fein | [ string](#string) | Federal Employer Identification Number of the producer's company. |
| co_code | [ string](#string) | Company code for the insurance carrier. |
| line_of_authority | [ string](#string) | Line of authority for this appointment (e.g., Life, Property, Casualty). Indicates what types of insurance the producer can sell. |
| loa_code | [ string](#string) | Code for the line of authority for this appointment. |
| status | [ string](#string) | Current status of the appointment (e.g., Active, Terminated). |
| termination_reason | [ string](#string) | Reason for termination if the appointment has been terminated. |
| status_reason_date | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Date associated with the current status or reason. |
| appointment_renewal_date | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Date when the appointment will renew. |
| agency_affiliations | [ string](#string) | Additional affiliations or roles the producer has with the agency. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer.NIPR.Biographic {#producerniprbiographic}
Biographic contains personal and identifying information about the producer.


| Field | Type | Description |
| ----- | ---- | ----------- |
| last_name | [ string](#string) | Last name of the producer as recorded in NIPR. |
| first_name | [ string](#string) | First name of the producer as recorded in NIPR. |
| middle_name | [ string](#string) | Middle name of the producer as recorded in NIPR. |
| date_of_birth | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | Date of birth of the producer. |
| fein | [ string](#string) | Federal Employer Identification Number if the producer is a business entity. |
| company_name | [ string](#string) | Company name if the producer is a business entity. |
| state_domicile | [ string](#string) | State of domicile (resident state) for the producer. This is the state where the producer is primarily located. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer.NIPR.License {#producerniprlicense}
License contains information about a producer's insurance license.


| Field | Type | Description |
| ----- | ---- | ----------- |
| license_number | [ string](#string) | The license number assigned by the state regulatory authority. |
| license_state | [ string](#string) | The state that issued the license. Typically a two-letter state code. |
| residency_status | [ string](#string) | Indicates whether this is a resident or non-resident license. Values are typically "Resident" or "Non-Resident". |
| active | [ bool](#bool) | Indicates whether the license is currently active. |
| status | [ Producer.NIPR.License.LicenseStatus](#producerniprlicenselicensestatus) | The current status of the license (valid, expired, etc.). |
| expiration_date | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | The date when the license will expire if not renewed. |
| updated_at | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | The last time this license information was updated from NIPR. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer.NIPR.ProducerRegulatoryInfo {#producerniprproducerregulatoryinfo}
ProducerRegulatoryInfo contains regulatory information about a producer,
including any regulatory actions taken against them.


| Field | Type | Description |
| ----- | ---- | ----------- |
| regulatory_actions_by_state | [map Producer.NIPR.ProducerRegulatoryInfo.RegulatoryActionsByStateEntry](#producerniprproducerregulatoryinforegulatoryactionsbystateentry) | Map of regulatory actions by state. The key is the state code, and the value is the regulatory action. |
| clearance_certification_info | [ string](#string) | Clearance certification information for the producer. |
| nasd_exam_details | [ string](#string) | Details about NASD/FINRA examinations taken by the producer. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer.NIPR.ProducerRegulatoryInfo.RegulatoryAction {#producerniprproducerregulatoryinforegulatoryaction}
RegulatoryAction represents a regulatory action taken against a producer.


| Field | Type | Description |
| ----- | ---- | ----------- |
| action_id | [ string](#string) | Unique identifier for the regulatory action. |
| origin_of_action | [ string](#string) | The regulatory body that originated the action. Typically a state insurance department or FINRA. |
| reason_for_action | [ string](#string) | The reason why the regulatory action was taken. |
| disposition | [ string](#string) | The outcome or resolution of the regulatory action. |
| date_of_action | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | The date when the regulatory action was taken. |
| effective_date | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | The date when the regulatory action became effective. |
| enter_date | [ google.protobuf.Timestamp](#googleprotobuftimestamp) | The date when the producer entered into the regulatory action. |
| file_ref | [ string](#string) | Reference number for the regulatory action file. |
| penalty_fine_forfeiture | [ string](#string) | Any financial penalties associated with the regulatory action. |
| length_of_order | [ string](#string) | Duration of any orders associated with the regulatory action. |
 <!-- end Fields -->
 <!-- end HasFields -->


## Producer.NIPR.ProducerRegulatoryInfo.RegulatoryActionsByStateEntry {#producerniprproducerregulatoryinforegulatoryactionsbystateentry}



| Field | Type | Description |
| ----- | ---- | ----------- |
| key | [ string](#string) | none |
| value | [ Producer.NIPR.ProducerRegulatoryInfo.RegulatoryAction](#producerniprproducerregulatoryinforegulatoryaction) | none |
 <!-- end Fields -->
 <!-- end HasFields -->


## RejectProducerRequest {#rejectproducerrequest}
RejectProducerRequest requests rejection of a producer in the onboarding process.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_id | [ string](#string) | The UUID of the producer to reject. Must be a valid UUID format. |
| reason | [ string](#string) | The reason for rejecting the producer. Must be non-empty to provide context for the rejection. |
 <!-- end Fields -->
 <!-- end HasFields -->


## RejectProducerResponse {#rejectproducerresponse}
RejectProducerResponse is the empty response returned after successfully rejecting a producer.

 <!-- end HasFields -->


## ResyncAgencyRequest {#resyncagencyrequest}
ResyncAgencyRequest is used to trigger a manual resynchronization of agency data.
This will re-fetch all data from the NIPR API for the agency and all associated producers.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to resynchronize. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ResyncAgencyResponse {#resyncagencyresponse}
ResyncAgencyResponse is the empty response returned after successfully triggering a resynchronization.

 <!-- end HasFields -->


## ResyncProducerRequest {#resyncproducerrequest}
ResyncProducerRequest is used to trigger a manual resynchronization of producer data.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_id | [ string](#string) | The UUID of the producer to resynchronize. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ResyncProducerResponse {#resyncproducerresponse}
ResyncProducerResponse is the empty response returned after successfully triggering a resynchronization.

 <!-- end HasFields -->


## SetExternalIDRequest {#setexternalidrequest}
SetExternalIDRequest is used to associate an external identifier with a producer, agency, or contact.
This allows integration with external systems that use different ID schemes.

Only one entity type can be specified.


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) entity_id.producer_id | [ string](#string) | The UUID of the producer to set an external ID for. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) entity_id.agency_id | [ string](#string) | The UUID of the agency to set an external ID for. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) entity_id.contact_id | [ string](#string) | The UUID of the contact to set an external ID for. |
| tenant_id | [ string](#string) | The external tenant identifier to associate with the entity. Required and must be non-empty. |
 <!-- end Fields -->
 <!-- end HasFields -->


## SetExternalIDResponse {#setexternalidresponse}
SetExternalIDResponse is the empty response returned after successfully setting an external ID.

 <!-- end HasFields -->


## StopSyncAgencyWithNIPRRequest {#stopsyncagencywithniprrequest}
StopSyncAgencyWithNIPRRequest is used to stop synchronizing an agency's data with the NIPR API.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to stop synchronizing. Must be a valid UUID format. |
| stop_all_producers | [ bool](#bool) | If true, all producers associated with the agency will be stopped from synchronizing. If false, only the agency will be stopped from synchronizing. |
 <!-- end Fields -->
 <!-- end HasFields -->


## StopSyncAgencyWithNIPRResponse {#stopsyncagencywithniprresponse}
StopSyncAgencyWithNIPRResponse is the empty response returned after successfully stopping the synchronization of an agency's data with the NIPR API.

 <!-- end HasFields -->


## StopSyncProducerWithNIPRRequest {#stopsyncproducerwithniprrequest}
StopSyncProducerWithNIPRRequest is used to stop synchronizing a producer's data with the NIPR API.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_id | [ string](#string) | The UUID of the producer to stop synchronizing. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## StopSyncProducerWithNIPRResponse {#stopsyncproducerwithniprresponse}
StopSyncProducerWithNIPRResponse is the empty response returned after successfully stopping the synchronization of a producer's data with the NIPR API.

 <!-- end HasFields -->


## SyncAgencyWithNIPRRequest {#syncagencywithniprrequest}
SyncAgencyWithNIPRRequest is used to synchronize an agency's data with the NIPR API.


| Field | Type | Description |
| ----- | ---- | ----------- |
| agency_id | [ string](#string) | The UUID of the agency to synchronize. Must be a valid UUID format. |
| sync_all_producers | [ bool](#bool) | If true, all producers associated with the agency will be synchronized. If false, only the agency will be synchronized. |
 <!-- end Fields -->
 <!-- end HasFields -->


## SyncAgencyWithNIPRResponse {#syncagencywithniprresponse}
SyncAgencyWithNIPRResponse is the empty response returned after successfully synchronizing an agency's data with the NIPR API.

 <!-- end HasFields -->


## SyncProducerWithNIPRRequest {#syncproducerwithniprrequest}
SyncProducerWithNIPRRequest is used to synchronize a producer's data with the NIPR API.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_id | [ string](#string) | The UUID of the producer to synchronize. Must be a valid UUID format. |
 <!-- end Fields -->
 <!-- end HasFields -->


## SyncProducerWithNIPRResponse {#syncproducerwithniprresponse}
SyncProducerWithNIPRResponse is the empty response returned after successfully synchronizing a producer's data with the NIPR API.

 <!-- end HasFields -->


## UpdateProducerRequest {#updateproducerrequest}
UpdateProducerRequest contains the fields that can be updated in a producer record.
Only information collected during the onboarding process can be updated.
Information from NIPR and other third-party sources cannot be updated directly.


| Field | Type | Description |
| ----- | ---- | ----------- |
| producer_id | [ string](#string) | The ID of the producer to update. Must be a valid UUID format. |
| producer | [ UpdateProducerRequest.Producer](#updateproducerrequestproducer) | The producer information to update. The field is required. |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateProducerRequest.Producer {#updateproducerrequestproducer}
Producer contains the fields that can be updated for a producer.
All fields are optional, allowing partial updates.


| Field | Type | Description |
| ----- | ---- | ----------- |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _first_name.first_name | [optional string](#string) | First name of the producer. If provided, must be non-empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _last_name.last_name | [optional string](#string) | Last name of the producer. If provided, must be non-empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _middle_name.middle_name | [optional string](#string) | Middle name of the producer. If provided, must be non-empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _email.email | [optional string](#string) | Email address of the producer. If provided, must be a valid email format. Must be unique within the tenant. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _npn.npn | [optional string](#string) | National Producer Number (NPN) of the producer. If provided, must be non-empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _phone.phone | [optional string](#string) | Phone number of the producer. If provided, must be a valid phone number format. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _street.street | [optional string](#string) | Street address of the producer. If provided, must be non-empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _city.city | [optional string](#string) | City of the producer. If provided, must be non-empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _state.state | [optional string](#string) | State of the producer. If provided, must be non-empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _zip.zip | [optional string](#string) | ZIP code of the producer's address. If provided, must be at least 5 characters. |
 <!-- end Fields -->
 <!-- end HasFields -->


## UpdateProducerResponse {#updateproducerresponse}
UpdateProducerResponse is the empty response returned after successfully updating a producer.

 <!-- end HasFields -->


## ValidateAgencyNPNRequest {#validateagencynpnrequest}
ValidateAgencyNPNRequest is used to validate an agency's National Producer Number.


| Field | Type | Description |
| ----- | ---- | ----------- |
| npn | [ string](#string) | The National Producer Number (NPN) to validate. Required and must be non-empty. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ValidateAgencyNPNResponse {#validateagencynpnresponse}
ValidateAgencyNPNResponse contains the result of validating an agency's NPN.


| Field | Type | Description |
| ----- | ---- | ----------- |
| valid | [ bool](#bool) | Indicates whether the NPN is valid. True if the NPN exists and is valid, false otherwise. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ValidateProducerNPNRequest {#validateproducernpnrequest}
ValidateProducerNPNRequest is used to validate a producer's National Producer Number.


| Field | Type | Description |
| ----- | ---- | ----------- |
| npn | [ string](#string) | The National Producer Number (NPN) to validate. Required and must be non-empty. |
| [**oneof**](https://developers.google.com/protocol-buffers/docs/proto3#oneof) _name.name | [optional string](#string) | Optional name of the producer to validate. If provided, the NPN will be validated against this name. |
 <!-- end Fields -->
 <!-- end HasFields -->


## ValidateProducerNPNResponse {#validateproducernpnresponse}
ValidateProducerNPNResponse contains the result of validating a producer's NPN.


| Field | Type | Description |
| ----- | ---- | ----------- |
| valid | [ bool](#bool) | Indicates whether the NPN is valid. True if the NPN exists and is valid, false otherwise. |
 <!-- end Fields -->
 <!-- end HasFields -->
 <!-- end messages -->

# Enums


## Agency.BankAccount.AccountType {#agencybankaccountaccounttype}
The type of account.

| Name | Number | Description |
| ---- | ------ | ----------- |
| ACCOUNT_TYPE_UNSPECIFIED | 0 | Default unspecified value. Avoid using this. |
| ACCOUNT_TYPE_CHECKING | 1 | Standard checking account. |
| ACCOUNT_TYPE_SAVINGS | 2 | Savings account. |




## EntityType {#entitytype}
EntityType defines the business entity type for an agency.

| Name | Number | Description |
| ---- | ------ | ----------- |
| ENTITY_TYPE_UNSPECIFIED | 0 | Default unspecified value. Do not use. |
| ENTITY_TYPE_SOLE_PROPRIETOR | 1 | An individual producer operating as their own agency. For this type, an agency NPN is not allowed, and additional producers are not supported. |
| ENTITY_TYPE_AGENCY | 2 | A standard insurance agency that can have multiple producers. For this type, either NPN or FEIN is required. |
| ENTITY_TYPE_ASK_DURING_ONBOARDING | 3 | Ask during onboarding because the entity type is not known when the agency onboarding url is created. The UI will ask the user to select the entity type. |




## NewAgencyRequest.Agency.BankAccount.AccountType {#newagencyrequestagencybankaccountaccounttype}


| Name | Number | Description |
| ---- | ------ | ----------- |
| ACCOUNT_TYPE_UNSPECIFIED | 0 | Default unspecified value. Avoid using this. |
| ACCOUNT_TYPE_CHECKING | 1 | Standard checking account |
| ACCOUNT_TYPE_SAVINGS | 2 | Savings account |




## NewAgencyRequest.Agency.PointOfContact.CommunicationRole {#newagencyrequestagencypointofcontactcommunicationrole}


| Name | Number | Description |
| ---- | ------ | ----------- |
| COMMUNICATION_ROLE_UNSPECIFIED | 0 | Default unspecified value. Avoid using this. |
| COMMUNICATION_ROLE_ACCOUNTING | 1 | Accounting role |
| COMMUNICATION_ROLE_LICENSING | 2 | Licensing role |
| COMMUNICATION_ROLE_REPORTING | 3 | Reporting role |
| COMMUNICATION_ROLE_SALES | 4 | Sales role |
| COMMUNICATION_ROLE_CUSTOMER_SERVICE | 5 | Customer service role |
| COMMUNICATION_ROLE_ALL | 6 | All roles |




## Producer.NIPR.License.LicenseStatus {#producerniprlicenselicensestatus}
LicenseStatus defines the possible statuses of an insurance license.

| Name | Number | Description |
| ---- | ------ | ----------- |
| LICENSE_STATUS_UNSPECIFIED | 0 | Default unspecified value. Avoid using this. |
| LICENSE_STATUS_EXPIRED | 1 | The license has expired and is no longer valid. |
| LICENSE_STATUS_VALID | 2 | License is currently active. |
| LICENSE_STATUS_NOT_ACTIVE | 3 | The license exists but is not in an active state. This could be due to suspension, revocation, or other reasons. |




## ProducerOnboardingState {#produceronboardingstate}
ProducerOnboardingState defines the possible states in the producer onboarding workflow.
This enum is deprecated and should not be used in new code.

| Name | Number | Description |
| ---- | ------ | ----------- |
| PRODUCER_ONBOARDING_STATE_UNSPECIFIED | 0 | none |
| PRODUCER_ONBOARDING_STATE_NEW | 1 | The producer has been added to the agency and is awaiting approval from the tenant. |
| PRODUCER_ONBOARDING_STATE_APPROVED_BY_TENANT | 2 | The producer has been approved by the tenant. |
| PRODUCER_ONBOARDING_STATE_REJECTED_BY_TENANT | 3 | The producer has been rejected by the tenant. |


 <!-- end Enums -->
 <!-- end Files -->

# Scalar Value Types

| .proto Type | Notes | C++ Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <div><h4 id="double" /></div><a name="double" /> double |  | double | double | float |
| <div><h4 id="float" /></div><a name="float" /> float |  | float | float | float |
| <div><h4 id="int32" /></div><a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <div><h4 id="int64" /></div><a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <div><h4 id="uint32" /></div><a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <div><h4 id="uint64" /></div><a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <div><h4 id="sint32" /></div><a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <div><h4 id="sint64" /></div><a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <div><h4 id="fixed32" /></div><a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <div><h4 id="fixed64" /></div><a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <div><h4 id="sfixed32" /></div><a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int |
| <div><h4 id="sfixed64" /></div><a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <div><h4 id="bool" /></div><a name="bool" /> bool |  | bool | boolean | boolean |
| <div><h4 id="string" /></div><a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <div><h4 id="bytes" /></div><a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str |

