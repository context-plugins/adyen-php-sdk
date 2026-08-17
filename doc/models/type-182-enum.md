
# Type 182 Enum

The type of legal entity.

Possible values: **individual**, **organization**, **soleProprietorship**, or **trust**.

## Enumeration

`Type182Enum`

## Fields

| Name |
|  --- |
| `INDIVIDUAL` |
| `ORGANIZATION` |
| `SOLEPROPRIETORSHIP` |
| `TRUST` |
| `UNINCORPORATEDPARTNERSHIP` |

## Example

```php
use AdyenLib\Models\Type182Enum;

$type182 = Type182Enum::SOLEPROPRIETORSHIP;
```

