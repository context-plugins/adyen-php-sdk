
# Merchant Details

## Structure

`MerchantDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `countryCode` | `?string` | Optional | 2-letter ISO 3166 country code of the card acceptor location.<br><br>> This parameter is required for the merchants who don't use Adyen as the payment authorisation gateway.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `enrolledIn3DSecure` | `?bool` | Optional | If true, indicates that the merchant is enrolled in 3D Secure for the card network. | getEnrolledIn3DSecure(): ?bool | setEnrolledIn3DSecure(?bool enrolledIn3DSecure): void |
| `mcc` | `?string` | Optional | The merchant category code (MCC) is a four-digit number which relates to a particular market segment. This code reflects the predominant activity that is conducted by the merchant.<br><br>The list of MCCs can be found [here](https://en.wikipedia.org/wiki/Merchant_category_code). | getMcc(): ?string | setMcc(?string mcc): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantDetailsBuilder;

$merchantDetails = MerchantDetailsBuilder::init()
    ->countryCode('countryCode8')
    ->enrolledIn3DSecure(false)
    ->mcc('mcc6')
    ->build();
```

