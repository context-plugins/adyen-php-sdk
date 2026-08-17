
# Stored Payment Method 6

## Structure

`StoredPaymentMethod6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type52Enum)`](../../doc/models/type-52-enum.md) | Optional | The payment method type. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\StoredPaymentMethod6Builder;
use AdyenLib\Models\Type52Enum;

$storedPaymentMethod6 = StoredPaymentMethod6Builder::init()
    ->checkoutAttemptId('checkoutAttemptId2')
    ->recurringDetailReference('recurringDetailReference6')
    ->sdkData('sdkData4')
    ->storedPaymentMethodId('storedPaymentMethodId0')
    ->type(Type52Enum::ALIPAY_PLUS_KAKAOPAY)
    ->build();
```

