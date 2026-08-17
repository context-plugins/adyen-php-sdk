
# Payment Method UPI Apps

## Structure

`PaymentMethodUPIApps`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appIdentifierInfo` | [`?AppIdentifierInfo1`](../../doc/models/app-identifier-info-1.md) | Optional | The app identifier information containing iOS scheme and Android package ID. | getAppIdentifierInfo(): ?AppIdentifierInfo1 | setAppIdentifierInfo(?AppIdentifierInfo1 appIdentifierInfo): void |
| `id` | `string` | Required | The unique identifier of this app, to submit in requests to /payments. | getId(): string | setId(string id): void |
| `name` | `string` | Required | A localized name of the app. | getName(): string | setName(string name): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentMethodUPIAppsBuilder;
use AdyenLib\Models\Builders\AppIdentifierInfo1Builder;

$paymentMethodUPIApps = PaymentMethodUPIAppsBuilder::init(
    'id2',
    'name2'
)
    ->appIdentifierInfo(
        AppIdentifierInfo1Builder::init()
            ->androidPackageId('androidPackageId8')
            ->iosScheme('iosScheme8')
            ->build()
    )
    ->build();
```

