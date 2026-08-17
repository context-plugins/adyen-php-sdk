
# Install Android Certificate Details

## Structure

`InstallAndroidCertificateDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `certificateId` | `?string` | Optional | The unique identifier of the certificate to be installed. | getCertificateId(): ?string | setCertificateId(?string certificateId): void |
| `type` | [`?string(Type42Enum)`](../../doc/models/type-42-enum.md) | Optional | Type of terminal action: Install an Android certificate.<br><br>**Default**: `Type42Enum::INSTALLANDROIDCERTIFICATE` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\InstallAndroidCertificateDetailsBuilder;
use AdyenLib\Models\Type42Enum;

$installAndroidCertificateDetails = InstallAndroidCertificateDetailsBuilder::init()
    ->certificateId('certificateId2')
    ->type(Type42Enum::INSTALLANDROIDCERTIFICATE)
    ->build();
```

