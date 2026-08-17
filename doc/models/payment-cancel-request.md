
# Payment Cancel Request

## Structure

`PaymentCancelRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `applicationInfo` | [`?ApplicationInfo`](../../doc/models/application-info.md) | Optional | Information about your application. For more details, see [Building Adyen solutions](https://docs.adyen.com/development-resources/building-adyen-solutions). | getApplicationInfo(): ?ApplicationInfo | setApplicationInfo(?ApplicationInfo applicationInfo): void |
| `merchantAccount` | `string` | Required | The merchant account that is used to process the payment. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `reference` | `?string` | Optional | Your reference for the cancel request. Maximum length: 80 characters. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentCancelRequestBuilder;
use AdyenLib\Models\Builders\ApplicationInfoBuilder;
use AdyenLib\Models\Builders\CommonField4Builder;
use AdyenLib\Models\Builders\CommonField1Builder;
use AdyenLib\Models\Builders\ExternalPlatformBuilder;
use AdyenLib\Models\Builders\CommonField2Builder;
use AdyenLib\Models\Builders\MerchantDeviceBuilder;

$paymentCancelRequest = PaymentCancelRequestBuilder::init(
    'merchantAccount2'
)
    ->applicationInfo(
        ApplicationInfoBuilder::init()
            ->adyenLibrary(
                CommonField4Builder::init()
                    ->name('name8')
                    ->version('version4')
                    ->build()
            )
            ->adyenPaymentSource(
                CommonField1Builder::init()
                    ->name('name2')
                    ->version('version8')
                    ->build()
            )
            ->externalPlatform(
                ExternalPlatformBuilder::init()
                    ->integrator('integrator0')
                    ->name('name4')
                    ->version('version0')
                    ->build()
            )
            ->merchantApplication(
                CommonField2Builder::init()
                    ->name('name2')
                    ->version('version8')
                    ->build()
            )
            ->merchantDevice(
                MerchantDeviceBuilder::init()
                    ->os('os4')
                    ->osVersion('osVersion6')
                    ->reference('reference8')
                    ->build()
            )
            ->build()
    )
    ->reference('reference8')
    ->build();
```

