
# Return Transfer Request

## Structure

`ReturnTransferRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains information about the amount to be returned. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `reference` | `?string` | Optional | Your internal reference for the return. If you don't provide this in the request, Adyen generates a unique reference. This reference is used in all communication with you about the instruction status.<br><br>We recommend using a unique value per instruction.<br>If you need to provide multiple references for a transaction, separate them with hyphens ("-").<br><br>**Constraints**: *Maximum Length*: `80` | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\ReturnTransferRequestBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$returnTransferRequest = ReturnTransferRequestBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)
    ->reference('reference2')
    ->build();
```

