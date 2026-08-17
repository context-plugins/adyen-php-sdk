
# Type 121 Enum

The type of the cashout transfer.

Possible values:

- **cashoutRepayment**: Corresponds to the transfer created to deduct the cashout amount after settlement.
- **cashoutFee**: Corresponds to the transfer created to debit the cashout fee form the user's balance account.

## Enumeration

`Type121Enum`

## Fields

| Name |
|  --- |
| `CASHOUTREPAYMENT` |
| `CASHOUTFEE` |

## Example

```php
use AdyenLib\Models\Type121Enum;

$type121 = Type121Enum::CASHOUTREPAYMENT;
```

