
# Uninstall Android Certificate Details

## Structure

`UninstallAndroidCertificateDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `certificateId` | `?string` | Optional | The unique identifier of the certificate to be uninstalled. | getCertificateId(): ?string | setCertificateId(?string certificateId): void |
| `type` | [`?string(Type81Enum)`](../../doc/models/type-81-enum.md) | Optional | Type of terminal action: Uninstall an Android certificate.<br><br>**Default**: `Type81Enum::UNINSTALLANDROIDCERTIFICATE` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\UninstallAndroidCertificateDetailsBuilder;
use AdyenLib\Models\Type81Enum;

$uninstallAndroidCertificateDetails = UninstallAndroidCertificateDetailsBuilder::init()
    ->certificateId('certificateId0')
    ->type(Type81Enum::UNINSTALLANDROIDCERTIFICATE)
    ->build();
```

