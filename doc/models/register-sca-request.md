
# Register SCA Request

## Structure

`RegisterSCARequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The name of the SCA device that you are registering. You can use it to help your users identify the device.<br><br>If you do not specify a `name`, Adyen automatically generates one. | getName(): ?string | setName(?string name): void |
| `paymentInstrumentId` | `string` | Required | The unique identifier of the payment instrument for which you are registering the SCA device. | getPaymentInstrumentId(): string | setPaymentInstrumentId(string paymentInstrumentId): void |
| `strongCustomerAuthentication` | [`DelegatedAuthenticationData1`](../../doc/models/delegated-authentication-data-1.md) | Required | Contains information required to register the SCA device. | getStrongCustomerAuthentication(): DelegatedAuthenticationData1 | setStrongCustomerAuthentication(DelegatedAuthenticationData1 strongCustomerAuthentication): void |

## Example

```php
use AdyenLib\Models\Builders\RegisterSCARequestBuilder;
use AdyenLib\Models\Builders\DelegatedAuthenticationData1Builder;

$registerSCARequest = RegisterSCARequestBuilder::init(
    'paymentInstrumentId6',
    DelegatedAuthenticationData1Builder::init(
        'sdkOutput4'
    )->build()
)
    ->name('name4')
    ->build();
```

