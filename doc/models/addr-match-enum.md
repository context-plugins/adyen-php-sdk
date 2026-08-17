
# Addr Match Enum

Indicates whether the cardholder shipping address and cardholder billing address are the same. Allowed values:

* **Y** — Shipping address matches billing address.
* **N** — Shipping address does not match billing address.

## Enumeration

`AddrMatchEnum`

## Fields

| Name |
|  --- |
| `Y` |
| `N` |

## Example

```php
use AdyenLib\Models\AddrMatchEnum;

$addrMatch = AddrMatchEnum::Y;
```

