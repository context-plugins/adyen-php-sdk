
# Afterpay

## Structure

`Afterpay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billingAddress` | `?string` | Optional | The address where to send the invoice. | getBillingAddress(): ?string | setBillingAddress(?string billingAddress): void |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `deliveryAddress` | `?string` | Optional | The address where the goods should be delivered. | getDeliveryAddress(): ?string | setDeliveryAddress(?string deliveryAddress): void |
| `personalDetails` | `?string` | Optional | Shopper name, date of birth, phone number, and email address. | getPersonalDetails(): ?string | setPersonalDetails(?string personalDetails): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`string(Type2Enum)`](../../doc/models/type-2-enum.md) | Required | **afterpay_default**<br><br>**Default**: `Type2Enum::AFTERPAY_DEFAULT` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AfterpayBuilder;
use AdyenLib\Models\Type2Enum;

$afterpay = AfterpayBuilder::init(
    Type2Enum::AFTERPAY_DEFAULT
)
    ->billingAddress('billingAddress8')
    ->checkoutAttemptId('checkoutAttemptId6')
    ->deliveryAddress('deliveryAddress6')
    ->personalDetails('personalDetails8')
    ->recurringDetailReference('recurringDetailReference0')
    ->build();
```

