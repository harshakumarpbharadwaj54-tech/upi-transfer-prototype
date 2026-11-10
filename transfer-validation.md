# UPI Transfer Validation Requirements

## Requirement TV-01: Validate transfer details
The transfer request must include a valid positive amount, a recipient, and an idempotency key.

## Requirement TV-02: Prevent duplicate debit on retry
If the same transfer request is retried with the same idempotency key, the system must not debit the account a second time.

## Test cases
- A valid amount, recipient, and new key are accepted for processing.
- A zero or negative amount is rejected.
- A missing recipient or idempotency key is rejected.
- Retrying a request with the same key must not create another debit.
