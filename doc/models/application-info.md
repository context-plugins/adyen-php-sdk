
# Application Info

Information about your application. For more details, see [Building Adyen solutions](https://docs.adyen.com/development-resources/building-adyen-solutions).

## Structure

`ApplicationInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adyenLibrary` | [`?CommonField4`](../../doc/models/common-field-4.md) | Optional | Adyen-developed software, such as libraries and plugins, used to interact with the Adyen API. For example, Magento plugin, Java API library, etc. | getAdyenLibrary(): ?CommonField4 | setAdyenLibrary(?CommonField4 adyenLibrary): void |
| `adyenPaymentSource` | [`?CommonField1`](../../doc/models/common-field-1.md) | Optional | Adyen-developed software to get payment details. For example, Checkout SDK, Secured Fields SDK, etc. | getAdyenPaymentSource(): ?CommonField1 | setAdyenPaymentSource(?CommonField1 adyenPaymentSource): void |
| `externalPlatform` | [`?ExternalPlatform`](../../doc/models/external-platform.md) | Optional | Third-party developed platform used to initiate payment requests. For example, Magento, Zuora, etc. | getExternalPlatform(): ?ExternalPlatform | setExternalPlatform(?ExternalPlatform externalPlatform): void |
| `merchantApplication` | [`?CommonField2`](../../doc/models/common-field-2.md) | Optional | Merchant developed software, such as cashier application, used to interact with the Adyen API. | getMerchantApplication(): ?CommonField2 | setMerchantApplication(?CommonField2 merchantApplication): void |
| `merchantDevice` | [`?MerchantDevice`](../../doc/models/merchant-device.md) | Optional | Merchant device information. | getMerchantDevice(): ?MerchantDevice | setMerchantDevice(?MerchantDevice merchantDevice): void |
| `shopperInteractionDevice` | [`?ShopperInteractionDevice`](../../doc/models/shopper-interaction-device.md) | Optional | Shopper interaction device, such as terminal, mobile device or web browser, to initiate payment requests. | getShopperInteractionDevice(): ?ShopperInteractionDevice | setShopperInteractionDevice(?ShopperInteractionDevice shopperInteractionDevice): void |

## Example

```php
use AdyenLib\Models\Builders\ApplicationInfoBuilder;
use AdyenLib\Models\Builders\CommonField4Builder;
use AdyenLib\Models\Builders\CommonField1Builder;
use AdyenLib\Models\Builders\ExternalPlatformBuilder;
use AdyenLib\Models\Builders\CommonField2Builder;
use AdyenLib\Models\Builders\MerchantDeviceBuilder;

$applicationInfo = ApplicationInfoBuilder::init()
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
    ->build();
```

