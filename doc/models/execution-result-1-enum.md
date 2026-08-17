
# Execution Result 1 Enum

The status of the payout execution.

Possible values:

- **succeeded**: The payout was sent successfully.
- **failed**: The payout could not be sent because an error occurred.
- **skipped**: The payout was not triggered as expected.

## Enumeration

`ExecutionResult1Enum`

## Fields

| Name |
|  --- |
| `FAILED` |
| `SUCCEEDED` |
| `SKIPPED` |

## Example

```php
use AdyenLib\Models\ExecutionResult1Enum;

$executionResult1 = ExecutionResult1Enum::SKIPPED;
```

