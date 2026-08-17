
# Calculate Grant Offer Request

## Structure

`CalculateGrantOfferRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The financing amount that the user selected from a dynamic offer. Adyen uses this amount to calculate a preliminary offer. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\CalculateGrantOfferRequestBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$calculateGrantOfferRequest = CalculateGrantOfferRequestBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

