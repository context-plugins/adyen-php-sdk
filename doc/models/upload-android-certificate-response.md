
# Upload Android Certificate Response

## Structure

`UploadAndroidCertificateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The unique identifier of the uploaded Android certificate. | getId(): ?string | setId(?string id): void |

## Example

```php
use AdyenLib\Models\Builders\UploadAndroidCertificateResponseBuilder;

$uploadAndroidCertificateResponse = UploadAndroidCertificateResponseBuilder::init()
    ->id('id6')
    ->build();
```

