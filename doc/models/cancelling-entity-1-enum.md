
# Cancelling Entity 1 Enum

The party that initiated the cancellation of the transaction.

Possible values: **merchant**, **cardholder**.

## Enumeration

`CancellingEntity1Enum`

## Fields

| Name |
|  --- |
| `MERCHANT` |
| `CARDHOLDER` |

## Example

```php
use AdyenLib\Models\CancellingEntity1Enum;

$cancellingEntity1 = CancellingEntity1Enum::MERCHANT;
```

