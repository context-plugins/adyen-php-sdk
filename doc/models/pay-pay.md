
# Pay Pay

## Structure

`PayPay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type40Enum)`](../../doc/models/type-40-enum.md) | Optional | **paypay**<br><br>**Default**: `Type40Enum::PAYPAY` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\PayPayBuilder;
use AdyenLib\Models\Type40Enum;

$payPay = PayPayBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId4')
    ->recurringDetailReference('recurringDetailReference8')
    ->sdkData('sdkData8')
    ->storedPaymentMethodId('storedPaymentMethodId2')
    ->type(Type40Enum::PAYPAY)
    ->build();
```

