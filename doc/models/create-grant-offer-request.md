
# Create Grant Offer Request

## Structure

`CreateGrantOfferRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The financing amount that the user selected from the dynamic offer. Adyen uses this amount to create a static offer. | getAmount(): Amount17 | setAmount(Amount17 amount): void |

## Example

```php
use AdyenLib\Models\Builders\CreateGrantOfferRequestBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$createGrantOfferRequest = CreateGrantOfferRequestBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)->build();
```

