
# Mobile Data 1

Information related to the mobile for the payment transaction.
If PaymentInstrumentType is Mobile.

## Structure

`MobileData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `mobileCountryCode` | `?int` | Optional | Identifies the country of a mobile phone operator.<br>If data available.<br><br>**Constraints**: `>= 3`, `<= 3` | getMobileCountryCode(): ?int | setMobileCountryCode(?int mobileCountryCode): void |
| `mobileNetworkCode` | `?int` | Optional | Identifies the mobile phone operator inside a country.<br>If data available.<br><br>**Constraints**: `>= 2`, `<= 3` | getMobileNetworkCode(): ?int | setMobileNetworkCode(?int mobileNetworkCode): void |
| `maskedMSISDN` | `?int` | Optional | Masked Mobile Subscriber Integrated Service Digital Network.<br>If data available. | getMaskedMSISDN(): ?int | setMaskedMSISDN(?int maskedMSISDN): void |
| `geolocation` | [`?Geolocation1`](../../doc/models/geolocation-1.md) | Optional | Geographic location specified by geographic or UTM coordinates.<br>If data available. | getGeolocation(): ?Geolocation1 | setGeolocation(?Geolocation1 geolocation): void |
| `protectedMobileData` | `?string` | Optional | Sensitive information related to the mobile phone, protected by CMS.<br>SensitiveMobileData. | getProtectedMobileData(): ?string | setProtectedMobileData(?string protectedMobileData): void |
| `sensitiveMobileData` | [`?SensitiveMobileData1`](../../doc/models/sensitive-mobile-data-1.md) | Optional | Sensitive information related to the mobile phone.<br>If unprotected mobile data. | getSensitiveMobileData(): ?SensitiveMobileData1 | setSensitiveMobileData(?SensitiveMobileData1 sensitiveMobileData): void |

## Example

```php
use AdyenLib\Models\Builders\MobileData1Builder;
use AdyenLib\Models\Builders\Geolocation1Builder;
use AdyenLib\Models\Builders\GeographicCoordinatesBuilder;
use AdyenLib\Models\Builders\UTMCoordinatesBuilder;

$mobileData1 = MobileData1Builder::init()
    ->mobileCountryCode(3)
    ->mobileNetworkCode(3)
    ->maskedMSISDN(220)
    ->geolocation(
        Geolocation1Builder::init()
            ->geographicCoordinates(
                GeographicCoordinatesBuilder::init(
                    'Latitude4',
                    'Longitude2'
                )->build()
            )
            ->uTMCoordinates(
                UTMCoordinatesBuilder::init(
                    'UTMZone6',
                    'UTMEastward0',
                    'UTMNorthward0'
                )->build()
            )->build()
    )
    ->protectedMobileData('ProtectedMobileData8')
    ->build();
```

