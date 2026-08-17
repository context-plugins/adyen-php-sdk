
# Sca Entity Type 1 Enum

The type of entity you are associating the device with.

Possible values: **accountHolder**, **legalEntity** or **paymentInstrument**.

## Enumeration

`ScaEntityType1Enum`

## Fields

| Name |
|  --- |
| `ACCOUNTHOLDER` |
| `LEGALENTITY` |
| `PAYMENTINSTRUMENT` |

## Example

```php
use AdyenLib\Models\ScaEntityType1Enum;

$scaEntityType1 = ScaEntityType1Enum::LEGALENTITY;
```

