# Non-Functional Requirements

## Performance

### NFR-001

95% of phone number validation requests shall complete within 1 second.

### NFR-002

95% of recipient search requests shall complete within 3 seconds.

### NFR-003

98% of transfer amount validation requests shall complete within 1 second.

### NFR-004

95% of available balance verification requests shall complete within 2 seconds.

### NFR-005

95% of transfer limit verification requests shall complete within 3 seconds.

### NFR-006

95% of transfer execution requests sent to the Account Service shall receive a response within 5 seconds.

### NFR-007

95% of transfer result messages shall be sent to the Notification Service within 5 seconds after the final transfer status is determined.

### NFR-008

95% of transfer limit information requests shall complete within 3 seconds.

### NFR-009

95% of transfer history requests shall complete within 5 seconds.


## Availability

### NFR-010

The system shall maintain at least 99.99% availability per calendar month, excluding scheduled maintenance.
