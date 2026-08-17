
# Status 14 Enum

The current status of the grant. Possible values: **Pending**, **Active**, **Repaid**, **WrittenOff**, **Failed**, **Revoked**.

## Enumeration

`Status14Enum`

## Fields

| Name |
|  --- |
| `PENDING` |
| `ACTIVE` |
| `REPAID` |
| `FAILED` |
| `WRITTENOFF` |
| `REVOKED` |

## Example

```php
use AdyenLib\Models\Status14Enum;

$status14 = Status14Enum::WRITTENOFF;
```

