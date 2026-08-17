
# Sub Type 11 Enum

The specific category of **other** dispute that you are raising.

Possible values: **atmDispute**, **cancelledGoodsServices**, **cancelledRecurring**, **counterfeit**, **creditNotProcessed**, **notAsDescribed**.

## Enumeration

`SubType11Enum`

## Fields

| Name |
|  --- |
| `ATMDISPUTE` |
| `CANCELLEDGOODSSERVICES` |
| `CANCELLEDRECURRING` |
| `CREDITNOTPROCESSED` |
| `COUNTERFEIT` |
| `NOTASDESCRIBED` |

## Example

```php
use AdyenLib\Models\SubType11Enum;

$subType11 = SubType11Enum::COUNTERFEIT;
```

