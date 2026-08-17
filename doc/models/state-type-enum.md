
# State Type Enum

The state to be updated.

> Permitted values are: `Processing`, `Payout`

## Enumeration

`StateTypeEnum`

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
use AdyenLib\Models\StateTypeEnum;

$stateType = StateTypeEnum::LIMITLESSPAYOUT;
```

