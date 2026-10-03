# Use Cases

## UC-001 — Find Transfer Recipient

### Description
The client searches for another bank client by phone number
to use them as the recipient of a transfer.

### Primary Actor
Bank Client

### Preconditions
- The client is authenticated.
- The client has an active bank account.

### Trigger
The client initiates a new transfer.

### Main Flow
1. The client opens the transfer section.
2. The system provides available recipient identification methods.
3. The client selects search by phone number.
4. The client enters the recipient's phone number.
5. The system validates the phone number.
6. The system searches for a client associated with the phone number.
7. The system displays the identified recipient.
8. The client selects the recipient.

### Alternative Flows

#### A1 — Invalid Phone Number
1. The system detects that the entered phone number is invalid.
2. The system informs the client about the invalid input.
3. The client enters a valid phone number or cancels the search.

#### A2 — Recipient Not Found
1. The system does not find a bank client associated with the entered phone number.
2. The system informs the client that the recipient was not found.
3. The client enters another phone number or selects another recipient identification method.

### Postconditions
- The recipient is successfully identified and selected for the transfer.


## UC-002 — Receive Transfer Notification

### Description

The client receives information about the result of a money transfer
without having to open the banking application.

### Primary Actor

Bank Client

### Supporting Actor

Notification Service

### Preconditions

- The client has an active bank account.
- The client has the banking application installed.
- The client's device is registered to receive notifications.

### Trigger

A money transfer involving the client reaches a final status.

### Main Flow

1. A money transfer is completed.
2. The Banking Transfer System determines the final status of the transfer.
3. The system sends the transfer result information to the Notification Service.
4. The Notification Service creates a notification for the client.
5. The Notification Service sends the notification to the client's device.
6. The client's device displays the notification.
7. The client sees the transfer result without opening the banking application.

### Alternative Flows

#### A1 — Notifications Are Disabled

1. The Notification Service attempts to send the notification.
2. The client's device does not display the notification because notifications are disabled.
3. The transfer information remains available inside the banking application.

#### A2 — Notification Service Unavailable

1. The Banking Transfer System cannot deliver the transfer result to the Notification Service.
2. The notification is not sent immediately.
3. The transfer result remains available in the banking application.

### Postconditions

- The transfer result is recorded in the banking system.
- If notifications are enabled, the client receives information about the transfer result.

## UC-003 — View Transfer Limit

### Description

The client views up-to-date information about the used and remaining monthly transfer limit.

### Primary Actor

Bank Client

### Supporting Actor

Account Service

### Preconditions

- The client is authenticated.
- The client has an active bank account.

### Trigger

The client requests information about their current transfer limit.

### Main Flow

1. The client opens the transfer limits section.
2. The system requests the client's current transfer limit information from the Account Service.
3. The Account Service determines the client's used transfer amount for the current monthly period.
4. The Account Service calculates the remaining transfer limit.
5. The Account Service returns the limit information to the system.
6. The system displays the used and remaining transfer limit to the client.

### Alternative Flows

#### A1 — Limit Information Unavailable

1. The system cannot retrieve the client's transfer limit information.
2. The system informs the client that the information is temporarily unavailable.
3. The use case ends.

### Postconditions

- The client receives the current monthly transfer limit information.
- The client's transfer limit remains unchanged.

## UC-004 — View Transfer History

### Description

The client views their transfer history for the previous 12 months.

### Primary Actor

Bank Client

### Supporting Actor

Account Service

### Preconditions

- The client is authenticated.
- The client has an active bank account.

### Trigger

The client requests to view their transfer history.

### Main Flow

1. The client opens the transfer history section.
2. The system requests the client's transfer history from the Account Service.
3. The Account Service retrieves transfers involving the client from the previous 12 months.
4. The Account Service returns the transfer history to the system.
5. The system displays the transfer history to the client.

### Alternative Flows

#### A1 — Transfer History Unavailable

1. The system cannot retrieve the client's transfer history.
2. The system informs the client that the information is temporarily unavailable.
3. The use case ends.

#### A2 — No Transfers Found

1. The Account Service finds no transfers for the client during the selected period.
2. The system informs the client that no transfer history is available for that period.

### Postconditions

- The client receives access to their available transfer history for the previous 12 months.
- No transfer data is modified.

## UC-005 — Transfer Money

### Description

The client transfers money to another client of the same bank.

### Primary Actor

Bank Client

### Supporting Actor

Account Service

### Preconditions

- The client is authenticated.
- The client has an active bank account.
- The recipient has been successfully identified.

### Trigger

The client initiates a money transfer to the selected recipient.

### Main Flow

1. The client enters the transfer amount.
2. The system validates the entered amount.
3. The system requests the sender's available balance from the Account Service.
4. The Account Service returns the current balance information.
5. The system verifies that the sender has sufficient funds.
6. The system verifies that the transfer does not exceed the client's transfer limit.
7. The system presents the transfer details to the client for confirmation.
8. The client confirms the transfer.
9. The system requests the Account Service to debit the sender's account and credit the recipient's account.
10. The Account Service completes the operation and returns the result.
11. The system records the transfer.
12. The system displays the successful transfer result to the client.

### Alternative Flows

#### A1 — Insufficient Funds

1. The system determines that the sender does not have sufficient funds.
2. The system informs the client that the available balance is insufficient.
3. The client enters a lower amount or cancels the transfer.

#### A2 — Transfer Limit Exceeded

1. The system determines that the transfer would exceed the client's available limit.
2. The system informs the client about the limit restriction.
3. The client enters a lower amount or cancels the transfer.

#### A3 — Transfer Failed

1. The Account Service cannot complete the debit or credit operation.
2. The system marks the transfer as failed.
3. The system informs the client that the transfer was not completed.

### Postconditions

- The transfer is recorded with its final status.
- If the transfer is successful, the sender's and recipient's account balances are updated.
- The client's available transfer limit is updated if applicable.
