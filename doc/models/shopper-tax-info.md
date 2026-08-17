
# Shopper Tax Info

## Structure

`ShopperTaxInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `taxCountryCode` | `string` | Required | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code associated with the provided tax identification number.<br>Currently used only for Indian PA-CB tax verification, when applicable.<br><br>**Constraints**: *Maximum Length*: `2` | getTaxCountryCode(): string | setTaxCountryCode(string taxCountryCode): void |
| `taxIdentificationNumber` | `string` | Required | The shopper’s tax identification number.<br><br>**Constraints**: *Maximum Length*: `20` | getTaxIdentificationNumber(): string | setTaxIdentificationNumber(string taxIdentificationNumber): void |

## Example

```php
use AdyenLib\Models\Builders\ShopperTaxInfoBuilder;

$shopperTaxInfo = ShopperTaxInfoBuilder::init(
    'taxCountryCode4',
    'taxIdentificationNumber4'
)->build();
```

