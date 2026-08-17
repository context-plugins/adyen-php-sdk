
# Refund Funds Transfer Request

## Structure

`RefundFundsTransferRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | The amount to be transferred. | getAmount(): Amount | setAmount(Amount amount): void |
| `merchantReference` | `?string` | Optional | A value that can be supplied at the discretion of the executing user in order to link multiple transactions to one another. | getMerchantReference(): ?string | setMerchantReference(?string merchantReference): void |
| `originalReference` | `string` | Required | A PSP reference of the original fund transfer. | getOriginalReference(): string | setOriginalReference(string originalReference): void |

## Example

```php
use AdyenLib\Models\Builders\RefundFundsTransferRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;

$refundFundsTransferRequest = RefundFundsTransferRequestBuilder::init(
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'originalReference2'
)
    ->merchantReference('merchantReference2')
    ->build();
```

