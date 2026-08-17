
# Payment Details

## Structure

`PaymentDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type43Enum)`](../../doc/models/type-43-enum.md) | Optional | The payment method type. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentDetailsBuilder;
use AdyenLib\Models\Type43Enum;

$paymentDetails = PaymentDetailsBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId2')
    ->sdkData('sdkData4')
    ->type(Type43Enum::PRIMEIROPAY_BOLETO)
    ->build();
```

