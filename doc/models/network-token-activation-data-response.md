
# Network Token Activation Data Response

## Structure

`NetworkTokenActivationDataResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sdkInput` | `?string` | Optional | A block of data that contains the activation data for a network token. This `sdkInput` is required to initialize Adyen's SDK for network token provisioning.<br><br>For more information, see the repositories for Adyen's SDKs for network token provisioning:<br><br>* [Adyen Apple Pay Provisioning SDK](https://github.com/Adyen/adyen-apple-pay-provisioning-ios).<br>* [Adyen Google Wallet Provisioning SDK](https://github.com/Adyen/adyen-issuing-android) | getSdkInput(): ?string | setSdkInput(?string sdkInput): void |

## Example

```php
use AdyenLib\Models\Builders\NetworkTokenActivationDataResponseBuilder;

$networkTokenActivationDataResponse = NetworkTokenActivationDataResponseBuilder::init()
    ->sdkInput('sdkInput6')
    ->build();
```

