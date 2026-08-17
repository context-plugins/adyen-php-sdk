
# Code Enum

The code for the status of the grant. Possible values:

- **Pending**
- **Active**
- **Repaid**
- **WrittenOff**
- **Failed**
- **Revoked**
- **Requested**
- **Reviewing**
- **Approved**
- **Rejected**
- **Cancelled**

## Enumeration

`CodeEnum`

## Fields

| Name |
|  --- |
| `PENDING` |
| `ACTIVE` |
| `REPAID` |
| `WRITTENOFF` |
| `FAILED` |
| `REVOKED` |
| `REQUESTED` |
| `REVIEWING` |
| `APPROVED` |
| `REJECTED` |
| `CANCELLED` |

## Example

```php
use AdyenLib\Models\CodeEnum;

$code = CodeEnum::CANCELLED;
```

