
# Account State Type Enum

The state required for the account holder.

> Permitted values: `Processing`, `Payout`.

## Enumeration

`AccountStateTypeEnum`

## Fields

| Name |
|  --- |
| `LIMITEDPAYOUT` |
| `LIMITEDPROCESSING` |
| `LIMITLESSPAYOUT` |
| `LIMITLESSPROCESSING` |
| `PAYOUT` |
| `PROCESSING` |

## Example

```php
use AdyenLib\Models\AccountStateTypeEnum;

$accountStateType = AccountStateTypeEnum::PAYOUT;
```

