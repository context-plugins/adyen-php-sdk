
# Store Filtration Mode 2 Enum

Specifies how payment methods should be filtered based on the `store` parameter:

- **exclusive**: Only payment methods belonging to the specified `store` are returned.
- **inclusive**: Payment methods from the `store` and those not associated with any other store are returned.

## Enumeration

`StoreFiltrationMode2Enum`

## Fields

| Name |
|  --- |
| `EXCLUSIVE` |
| `INCLUSIVE` |
| `SKIPFILTER` |

## Example

```php
use AdyenLib\Models\StoreFiltrationMode2Enum;

$storeFiltrationMode2 = StoreFiltrationMode2Enum::INCLUSIVE;
```

