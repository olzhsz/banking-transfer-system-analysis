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

A2 — Notification Service unavailable

1. The Banking Transfer System cannot deliver the transfer result to the Notification Service.
2. The notification is not sent immediately.
3. The transfer result remains available in the banking application.

### Postconditions

- The transfer result is recorded in the banking system.
- If notifications are enabled, the client receives information about the transfer result.
