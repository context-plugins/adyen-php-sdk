
# Grant Offer Fee 1

Contains information about the fee that your user would pay for the grant.

## Structure

`GrantOfferFee1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains the amount of the offer fee. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `aprBasisPoints` | `?int` | Optional | Annual Percentage Rate (APR) of the offer. The percentage is expressed in [basis points](https://www.investopedia.com/terms/b/basispoint.asp). | getAprBasisPoints(): ?int | setAprBasisPoints(?int aprBasisPoints): void |

## Example

```php
use AdyenLib\Models\Builders\GrantOfferFee1Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$grantOfferFee1 = GrantOfferFee1Builder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build()
)
    ->aprBasisPoints(216)
    ->build();
```

