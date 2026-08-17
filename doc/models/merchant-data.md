
# Merchant Data

## Structure

`MerchantData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acquirerId` | `?string` | Optional | The unique identifier of the merchant's acquirer. | getAcquirerId(): ?string | setAcquirerId(?string acquirerId): void |
| `mcc` | `?string` | Optional | The merchant category code. | getMcc(): ?string | setMcc(?string mcc): void |
| `merchantId` | `?string` | Optional | The unique identifier of the merchant. | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `nameLocation` | [`?NameLocation2`](../../doc/models/name-location-2.md) | Optional | Contains the name and location of the merchant. | getNameLocation(): ?NameLocation2 | setNameLocation(?NameLocation2 nameLocation): void |
| `postalCode` | `?string` | Optional | The postal code of the merchant. | getPostalCode(): ?string | setPostalCode(?string postalCode): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantDataBuilder;
use AdyenLib\Models\Builders\NameLocation2Builder;

$merchantData = MerchantDataBuilder::init()
    ->acquirerId('acquirerId6')
    ->mcc('mcc4')
    ->merchantId('merchantId0')
    ->nameLocation(
        NameLocation2Builder::init()
            ->city('city6')
            ->country('country8')
            ->countryOfOrigin('countryOfOrigin0')
            ->name('name4')
            ->rawData('rawData0')
            ->build()
    )
    ->postalCode('postalCode6')
    ->build();
```

