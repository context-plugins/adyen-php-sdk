
# Balance Transfer Request

## Structure

`BalanceTransferRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The amount of the transfer. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `fromMerchant` | `string` | Required | The unique identifier of the source merchant account from which funds are deducted.<br><br>**Constraints**: *Minimum Length*: `1` | getFromMerchant(): string | setFromMerchant(string fromMerchant): void |
| `reference` | `?string` | Optional | A reference for the balance transfer. Maximum length: 80 characters.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `80` | getReference(): ?string | setReference(?string reference): void |
| `toMerchant` | `string` | Required | The unique identifier of the destination merchant account to which funds are transferred.<br><br>**Constraints**: *Minimum Length*: `1` | getToMerchant(): string | setToMerchant(string toMerchant): void |
| `type` | [`string(BalanceTransferType2Enum)`](../../doc/models/balance-transfer-type-2-enum.md) | Required | The type of balance transfer. Possible values: **tax**, **fee**, **terminalSale**, **credit**, **debit**, and **adjustment**. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceTransferRequestBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\BalanceTransferType2Enum;

$balanceTransferRequest = BalanceTransferRequestBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    'fromMerchant8',
    'toMerchant8',
    BalanceTransferType2Enum::TERMINALSALE
)
    ->reference('reference6')
    ->build();
```

