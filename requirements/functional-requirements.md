
# Functional Requirements

## Recipient Search

### FR-001

The system shall validate the entered phone number.

### FR-002

The system shall search for a bank client associated with the provided phone number.

### FR-003

The system shall display the identified recipient.

### FR-004

The system shall inform the client if the entered phone number is invalid.

### FR-005

The system shall inform the client if no recipient is found.

## Money Transfer

### FR-006

The system shall validate the entered transfer amount.

### FR-007

The system shall retrieve the sender's available balance from the Account Service.

### FR-008

The system shall verify that the sender has sufficient funds.

### FR-009

The system shall verify that the transfer does not exceed the client's available transfer limit.

### FR-010

The system shall present the transfer details to the client for confirmation.

### FR-011

The system shall request the Account Service to debit the sender's account and credit the recipient's account.

### FR-012

The system shall record the transfer and its final status.

### FR-013

The system shall display the successful transfer result to the client.

### FR-014

The system shall inform the client if the available balance is insufficient.

### FR-015

The system shall inform the client if the transfer would exceed the available transfer limit.

### FR-016

The system shall mark the transfer as failed and inform the client if the Account Service cannot complete the debit or credit operation.

## Transfer Notifications

### FR-017

The system shall determine the final status of the transfer.

### FR-018

The system shall send the transfer result information to the Notification Service.

## Transfer Limits

### FR-019

The system shall retrieve the client's current transfer limit information from the Account Service.

### FR-020

The system shall display the used and remaining monthly transfer limit to the client.

### FR-021

The system shall inform the client if transfer limit information is temporarily unavailable.

## Transfer History

### FR-022

The system shall retrieve the authenticated client's transfer history from the Account Service.

### FR-023

The system shall retrieve transfer history for the previous 12 months.

### FR-024

The system shall display only transfers in which the authenticated client participated as the sender or recipient.

### FR-025

The system shall display the available transfer history to the client.

### FR-026

The system shall inform the client if transfer history information is temporarily unavailable.

### FR-027

The system shall inform the client if no transfers are available for the requested period.
