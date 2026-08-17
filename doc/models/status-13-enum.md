
# Status 13 Enum

The status of the request for PIN change.

Possible values: **completed**, **pending**, **unavailable**.

## Enumeration

`Status13Enum`

## Fields

| Name |
|  --- |
| `COMPLETED` |
| `PENDING` |
| `UNAVAILABLE` |

## Example

```php
use AdyenLib\Models\Status13Enum;

$status13 = Status13Enum::UNAVAILABLE;
```

