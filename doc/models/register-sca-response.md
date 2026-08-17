
# Register SCA Response

## Structure

`RegisterSCAResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The unique identifier of the SCA device you are registering. | getId(): ?string | setId(?string id): void |
| `paymentInstrumentId` | `?string` | Optional | The unique identifier of the payment instrument for which you are registering the SCA device. | getPaymentInstrumentId(): ?string | setPaymentInstrumentId(?string paymentInstrumentId): void |
| `sdkInput` | `?string` | Optional | A string that you must pass to the authentication SDK to continue with the registration process.<br><br>**Constraints**: *Maximum Length*: `20000` | getSdkInput(): ?string | setSdkInput(?string sdkInput): void |
| `success` | `?bool` | Optional | Specifies if the registration was initiated successfully. | getSuccess(): ?bool | setSuccess(?bool success): void |

## Example

```php
use AdyenLib\Models\Builders\RegisterSCAResponseBuilder;

$registerSCAResponse = RegisterSCAResponseBuilder::init()
    ->id('id4')
    ->paymentInstrumentId('paymentInstrumentId6')
    ->sdkInput('sdkInput8')
    ->success(false)
    ->build();
```

