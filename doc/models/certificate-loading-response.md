
# Certificate Loading Response

## Structure

`CertificateLoadingResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The unique identifier of the communication session. | getId(): ?string | setId(?string id): void |
| `installationId` | `?string` | Optional | The unique identifier of the SDK installation. If you create the [Terminal API](https://docs.adyen.com/point-of-sale/design-your-integration/terminal-api/) transaction request on your backend, use this as the `POIID` in the `MessageHeader` of the request. | getInstallationId(): ?string | setInstallationId(?string installationId): void |
| `merchantAccount` | `?string` | Optional | The unique identifier of your merchant account. | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |
| `sdkData` | `?string` | Optional | The data that the SDK uses to authenticate responses from the Adyen payments platform. Pass this value to your POS app. | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `store` | `?string` | Optional | The reference of the store that the transactions are processed for. | getStore(): ?string | setStore(?string store): void |

## Example

```php
use AdyenLib\Models\Builders\CertificateLoadingResponseBuilder;

$certificateLoadingResponse = CertificateLoadingResponseBuilder::init()
    ->id('id0')
    ->installationId('installationId6')
    ->merchantAccount('merchantAccount2')
    ->sdkData('sdkData0')
    ->store('store0')
    ->build();
```

