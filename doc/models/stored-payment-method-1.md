
# Stored Payment Method 1

## Structure

`StoredPaymentMethod1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type27Enum)`](../../doc/models/type-27-enum.md) | Optional | **sepadirectdebit**<br><br>**Default**: `Type27Enum::SEPADIRECTDEBIT` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\StoredPaymentMethod1Builder;
use AdyenLib\Models\Type27Enum;

$storedPaymentMethod1 = StoredPaymentMethod1Builder::init()
    ->checkoutAttemptId('checkoutAttemptId0')
    ->recurringDetailReference('recurringDetailReference4')
    ->sdkData('sdkData6')
    ->storedPaymentMethodId('storedPaymentMethodId8')
    ->type(Type27Enum::SEPADIRECTDEBIT)
    ->build();
```

