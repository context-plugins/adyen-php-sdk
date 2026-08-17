
# Cash Out Transfer

## Structure

`CashOutTransfer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The amount of the cashout instruction transaction, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `id` | `string` | Required | The reference of the cashout transfer. | getId(): string | setId(string id): void |
| `type` | [`string(Type121Enum)`](../../doc/models/type-121-enum.md) | Required | The type of the cashout transfer.<br><br>Possible values:<br><br>- **cashoutRepayment**: Corresponds to the transfer created to deduct the cashout amount after settlement.<br>- **cashoutFee**: Corresponds to the transfer created to debit the cashout fee form the user's balance account. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\CashOutTransferBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Type121Enum;

$cashOutTransfer = CashOutTransferBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    'id2',
    Type121Enum::CASHOUTREPAYMENT
)->build();
```

