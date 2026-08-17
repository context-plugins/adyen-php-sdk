
# Identification Type Enum

The type of the identification.

Possible values: **iban**, **routingNumber**, **sortCode**, **bic**.

## Enumeration

`IdentificationTypeEnum`

## Fields

| Name |
|  --- |
| `BIC` |
| `IBAN` |
| `ROUTINGNUMBER` |
| `SORTCODE` |

## Example

```php
use AdyenLib\Models\IdentificationTypeEnum;

$identificationType = IdentificationTypeEnum::BIC;
```

