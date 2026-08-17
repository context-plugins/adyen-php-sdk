
# Type 110 Enum

The [type of legal arrangement](https://docs.adyen.com/classic-platforms/verification-process/legal-arrangements#types-of-legal-arrangements).

Possible values:

- **Association**

- **Partnership**

- **SoleProprietorship**

- **Trust**

## Enumeration

`Type110Enum`

## Fields

| Name |
|  --- |
| `ASSOCIATION` |
| `PARTNERSHIP` |
| `SOLEPROPRIETORSHIP` |
| `TRUST` |

## Example

```php
use AdyenLib\Models\Type110Enum;

$type110 = Type110Enum::SOLEPROPRIETORSHIP;
```

