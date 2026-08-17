
# Donation Amount 1

The default amount for donations.

## Structure

`DonationAmount1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amounts` | `int[]` | Required | The donation amounts in minor units. The list must contain at least one amount and no more than three amounts.<br><br>**Constraints**: *Minimum Items*: `1`, *Maximum Items*: `3` | getAmounts(): array | setAmounts(array amounts): void |
| `currencyCode` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes#currency-codes).<br><br>**Constraints**: *Pattern*: `^[A-Z]{3}$` | getCurrencyCode(): string | setCurrencyCode(string currencyCode): void |

## Example

```php
use AdyenLib\Models\Builders\DonationAmount1Builder;

$donationAmount1 = DonationAmount1Builder::init(
    [
        248,
        249,
        250
    ],
    'currencyCode2'
)->build();
```

