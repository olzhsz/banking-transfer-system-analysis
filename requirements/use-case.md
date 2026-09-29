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
