
# Three DS 2 Card Range Detail

## Structure

`ThreeDS2CardRangeDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acsInfoInd` | `?(string[])` | Optional | Provides additional information to the 3DS Server.<br>Possible values:<br><br>- 01 (Authentication is available at ACS)<br>- 02 (Attempts supported by ACS or DS)<br>- 03 (Decoupled authentication supported)<br>- 04 (Whitelisting supported) | getAcsInfoInd(): ?array | setAcsInfoInd(?array acsInfoInd): void |
| `brandCode` | `?string` | Optional | Card brand. | getBrandCode(): ?string | setBrandCode(?string brandCode): void |
| `endRange` | `?string` | Optional | BIN end range. | getEndRange(): ?string | setEndRange(?string endRange): void |
| `startRange` | `?string` | Optional | BIN start range. | getStartRange(): ?string | setStartRange(?string startRange): void |
| `threeDS2Versions` | `?(string[])` | Optional | Supported 3D Secure protocol versions | getThreeDS2Versions(): ?array | setThreeDS2Versions(?array threeDS2Versions): void |
| `threeDSMethodURL` | `?string` | Optional | In a 3D Secure 2 browser-based flow, this is the URL where you should send the device fingerprint to. | getThreeDSMethodURL(): ?string | setThreeDSMethodURL(?string threeDSMethodURL): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDS2CardRangeDetailBuilder;

$threeDS2CardRangeDetail = ThreeDS2CardRangeDetailBuilder::init()
    ->acsInfoInd(
        [
            'acsInfoInd5',
            'acsInfoInd6'
        ]
    )
    ->brandCode('brandCode2')
    ->endRange('endRange4')
    ->startRange('startRange6')
    ->threeDS2Versions(
        [
            'threeDS2Versions3'
        ]
    )
    ->build();
```

