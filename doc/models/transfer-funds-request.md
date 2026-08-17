
# Transfer Funds Request

## Structure

`TransferFundsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | The amount to be transferred. | getAmount(): Amount | setAmount(Amount amount): void |
| `destinationAccountCode` | `string` | Required | The code of the account to which the funds are to be credited.<br><br>> The state of the Account Holder of this account must be Active. | getDestinationAccountCode(): string | setDestinationAccountCode(string destinationAccountCode): void |
| `merchantReference` | `?string` | Optional | A value that can be supplied at the discretion of the executing user in order to link multiple transactions to one another. | getMerchantReference(): ?string | setMerchantReference(?string merchantReference): void |
| `sourceAccountCode` | `string` | Required | The code of the account from which the funds are to be debited.<br><br>> The state of the Account Holder of this account must be Active and allow payouts. | getSourceAccountCode(): string | setSourceAccountCode(string sourceAccountCode): void |
| `transferCode` | `string` | Required | The code related to the type of transfer being performed.<br><br>> The permitted codes differ for each platform account and are defined in their service level agreement. | getTransferCode(): string | setTransferCode(string transferCode): void |

## Example

```php
use AdyenLib\Models\Builders\TransferFundsRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;

$transferFundsRequest = TransferFundsRequestBuilder::init(
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'destinationAccountCode6',
    'sourceAccountCode6',
    'transferCode8'
)
    ->merchantReference('merchantReference6')
    ->build();
```

