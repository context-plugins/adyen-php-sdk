
# Status 16 Enum

The new status of the network token. Possible values: **active**, **suspended**, **closed**. The **closed** status is final and cannot be changed.

## Enumeration

`Status16Enum`

## Fields

| Name |
|  --- |
| `ACTIVE` |
| `SUSPENDED` |
| `CLOSED` |

## Example

```php
use AdyenLib\Models\Status16Enum;

$status16 = Status16Enum::ACTIVE;
```

