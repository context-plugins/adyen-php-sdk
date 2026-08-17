
# Transfer Notification Merchant Data 2

Contains information about the merchant.

## Structure

`TransferNotificationMerchantData2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acquirerId` | `?string` | Optional | The unique identifier of the merchant's acquirer. | getAcquirerId(): ?string | setAcquirerId(?string acquirerId): void |
| `city` | `?string` | Optional | The city where the merchant is located. | getCity(): ?string | setCity(?string city): void |
| `country` | `?string` | Optional | The country where the merchant is located. | getCountry(): ?string | setCountry(?string country): void |
| `countryCode` | `?string` | Optional | The two-character country code of the merchant's location, in [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) format. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `mcc` | `?string` | Optional | The merchant category code. | getMcc(): ?string | setMcc(?string mcc): void |
| `merchantId` | `?string` | Optional | The unique identifier of the merchant. | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `name` | `?string` | Optional | The name of the merchant's shop or service. | getName(): ?string | setName(?string name): void |
| `postalCode` | `?string` | Optional | The postal code of the merchant. | getPostalCode(): ?string | setPostalCode(?string postalCode): void |

## Example

```php
use AdyenLib\Models\Builders\TransferNotificationMerchantData2Builder;

$transferNotificationMerchantData2 = TransferNotificationMerchantData2Builder::init()
    ->acquirerId('acquirerId0')
    ->city('city8')
    ->country('country2')
    ->countryCode('countryCode4')
    ->mcc('mcc8')
    ->build();
```

