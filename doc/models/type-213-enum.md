
# Type 213 Enum

The type of legal entity.

Possible values: **individual**, **organization**, **soleProprietorship**, or **trust**.

## Enumeration

`Type213Enum`

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
use AdyenLib\Models\Type213Enum;

$type213 = Type213Enum::UNINCORPORATEDPARTNERSHIP;
```

