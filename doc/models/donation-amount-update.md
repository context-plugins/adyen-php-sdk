
# Donation Amount Update

## Structure

`DonationAmountUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amounts` | `?(int[])` | Optional | The donation amounts in minor units. The list must contain at least one amount and no more than three amounts.<br><br>**Constraints**: *Minimum Items*: `1`, *Maximum Items*: `3` | getAmounts(): ?array | setAmounts(?array amounts): void |
| `currencyCode` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes).<br><br>**Constraints**: *Pattern*: `^[A-Z]{3}$` | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |

## Example

```php
use AdyenLib\Models\Builders\DonationAmountUpdateBuilder;

$donationAmountUpdate = DonationAmountUpdateBuilder::init()
    ->amounts(
        [
            96,
            97
        ]
    )
    ->currencyCode('currencyCode8')
    ->build();
```

