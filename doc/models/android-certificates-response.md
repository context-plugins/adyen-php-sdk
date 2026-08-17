
# Android Certificates Response

## Structure

`AndroidCertificatesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(AndroidCertificate[])`](../../doc/models/android-certificate.md) | Optional | Uploaded Android certificates for Android payment terminals. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\AndroidCertificatesResponseBuilder;
use AdyenLib\Models\Builders\AndroidCertificateBuilder;
use AdyenLib\Utils\DateTimeHelper;

$androidCertificatesResponse = AndroidCertificatesResponseBuilder::init()
    ->data(
        [
            AndroidCertificateBuilder::init(
                'id0'
            )
                ->description('description0')
                ->extension('extension6')
                ->name('name0')
                ->notAfter(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->notBefore(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->build()
        ]
    )
    ->build();
```

