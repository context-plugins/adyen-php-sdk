
# Three DS Availability Response

## Structure

`ThreeDSAvailabilityResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `binDetails` | [`?BinDetail1`](../../doc/models/bin-detail-1.md) | Optional | Bin Group Details | getBinDetails(): ?BinDetail1 | setBinDetails(?BinDetail1 binDetails): void |
| `dsPublicKeys` | [`?(DSPublicKeyDetail[])`](../../doc/models/ds-public-key-detail.md) | Optional | List of Directory Server (DS) public keys. | getDsPublicKeys(): ?array | setDsPublicKeys(?array dsPublicKeys): void |
| `threeDS1Supported` | `?bool` | Optional | Indicator if 3D Secure 1 is supported. | getThreeDS1Supported(): ?bool | setThreeDS1Supported(?bool threeDS1Supported): void |
| `threeDS2CardRangeDetails` | [`?(ThreeDS2CardRangeDetail[])`](../../doc/models/three-ds-2-card-range-detail.md) | Optional | List of brand and card range pairs. | getThreeDS2CardRangeDetails(): ?array | setThreeDS2CardRangeDetails(?array threeDS2CardRangeDetails): void |
| `threeDS2supported` | `?bool` | Optional | Indicator if 3D Secure 2 is supported. | getThreeDS2supported(): ?bool | setThreeDS2supported(?bool threeDS2supported): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDSAvailabilityResponseBuilder;
use AdyenLib\Models\Builders\BinDetail1Builder;
use AdyenLib\Models\Builders\DSPublicKeyDetailBuilder;
use AdyenLib\Models\Builders\ThreeDS2CardRangeDetailBuilder;

$threeDSAvailabilityResponse = ThreeDSAvailabilityResponseBuilder::init()
    ->binDetails(
        BinDetail1Builder::init()
            ->issuerCountry('issuerCountry8')
            ->build()
    )
    ->dsPublicKeys(
        [
            DSPublicKeyDetailBuilder::init()
                ->brand('brand6')
                ->directoryServerId('directoryServerId6')
                ->fromSDKVersion('fromSDKVersion8')
                ->publicKey('publicKey0')
                ->rootCertificates('rootCertificates4')
                ->build()
        ]
    )
    ->threeDS1Supported(false)
    ->threeDS2CardRangeDetails(
        [
            ThreeDS2CardRangeDetailBuilder::init()
                ->acsInfoInd(
                    [
                        'acsInfoInd1',
                        'acsInfoInd0',
                        'acsInfoInd9'
                    ]
                )
                ->brandCode('brandCode6')
                ->endRange('endRange2')
                ->startRange('startRange0')
                ->threeDS2Versions(
                    [
                        'threeDS2Versions9'
                    ]
                )
                ->build()
        ]
    )
    ->threeDS2supported(false)
    ->build();
```

