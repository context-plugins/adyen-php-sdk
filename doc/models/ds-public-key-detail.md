
# DS Public Key Detail

## Structure

`DSPublicKeyDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `brand` | `?string` | Optional | Card brand. | getBrand(): ?string | setBrand(?string brand): void |
| `directoryServerId` | `?string` | Optional | Directory Server (DS) identifier. | getDirectoryServerId(): ?string | setDirectoryServerId(?string directoryServerId): void |
| `fromSDKVersion` | `?string` | Optional | The version of the mobile 3D Secure 2 SDK. For the possible values, refer to the versions in [Adyen 3DS2 Android](https://github.com/Adyen/adyen-3ds2-android/releases) and [Adyen 3DS2 iOS](https://github.com/Adyen/adyen-3ds2-ios/releases). | getFromSDKVersion(): ?string | setFromSDKVersion(?string fromSDKVersion): void |
| `publicKey` | `?string` | Optional | Public key. The 3D Secure 2 SDK encrypts the device information by using the DS public key. | getPublicKey(): ?string | setPublicKey(?string publicKey): void |
| `rootCertificates` | `?string` | Optional | Directory Server root certificates. The 3D Secure 2 SDK verifies the ACS signed content using the rootCertificates. | getRootCertificates(): ?string | setRootCertificates(?string rootCertificates): void |

## Example

```php
use AdyenLib\Models\Builders\DSPublicKeyDetailBuilder;

$dSPublicKeyDetail = DSPublicKeyDetailBuilder::init()
    ->brand('brand2')
    ->directoryServerId('directoryServerId2')
    ->fromSDKVersion('fromSDKVersion4')
    ->publicKey('publicKey6')
    ->rootCertificates('rootCertificates0')
    ->build();
```

