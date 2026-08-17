
# Sca Entity Type 4 Enum

The type of the entity that you are associating with the SCA device.

Possible values: **accountHolder**, **legalEntity** or **paymentInstrument**.

## Enumeration

`ScaEntityType4Enum`

## Fields

| Name |
|  --- |
| `ACCOUNTHOLDER` |
| `LEGALENTITY` |
| `PAYMENTINSTRUMENT` |

## Example

```php
use AdyenLib\Models\ScaEntityType4Enum;

$scaEntityType4 = ScaEntityType4Enum::LEGALENTITY;
```

