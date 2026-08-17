
# Status 32 Enum

The status of the check.

Possible values: **AWAITING_DATA** , **DATA_PROVIDED**, **FAILED**, **INVALID_DATA**, **PASSED**, **PENDING**, **RETRY_LIMIT_REACHED**.

## Enumeration

`Status32Enum`

## Fields

| Name |
|  --- |
| `AWAITING_DATA` |
| `DATA_PROVIDED` |
| `FAILED` |
| `INVALID_DATA` |
| `PASSED` |
| `PENDING` |
| `PENDING_REVIEW` |
| `RETRY_LIMIT_REACHED` |
| `UNCHECKED` |

## Example

```php
use AdyenLib\Models\Status32Enum;

$status32 = Status32Enum::UNCHECKED;
```

