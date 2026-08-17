
# Certificate Loading Request

## Structure

`CertificateLoadingRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The unique identifier of your merchant account. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `setupToken` | `string` | Required | The setup token provided by the SDK in a Mobile solution for in-person payments.<br><br>- When using the Android SDK, obtain the token through the `MerchantAuthenticationService.authenticate(setupToken)` callback of `AuthenticationService`.<br>- When using the iOS SDK, obtain the token through the `PaymentServiceDelegate.register(with:)` callback of `PaymentServiceDelegate`. | getSetupToken(): string | setSetupToken(string setupToken): void |
| `store` | `?string` | Optional | The reference of the store that you want to process transactions for. Do not include this parameter if your account structure uses merchant accounts as stores, or if you are a registered payment facilitator. | getStore(): ?string | setStore(?string store): void |
| `subMerchantData` | [`?SubMerchantData21`](../../doc/models/sub-merchant-data-21.md) | Optional | The details of the sub-merchant that you want to process transactions for.Required if you are a registered payment facilitator. Do not include this parameter if you are not a payment facilitator. | getSubMerchantData(): ?SubMerchantData21 | setSubMerchantData(?SubMerchantData21 subMerchantData): void |

## Example

```php
use AdyenLib\Models\Builders\CertificateLoadingRequestBuilder;
use AdyenLib\Models\Builders\SubMerchantData21Builder;

$certificateLoadingRequest = CertificateLoadingRequestBuilder::init(
    'merchantAccount6',
    'setupToken8'
)
    ->store('store8')
    ->subMerchantData(
        SubMerchantData21Builder::init(
            'displayName4',
            'id8',
            'mcc8',
            'name8'
        )
            ->city('city2')
            ->country('country2')
            ->email('email8')
            ->phoneNumber('phoneNumber2')
            ->postalCode('postalCode0')
            ->build()
    )
    ->build();
```

