
# Rakuten Pay

## Structure

`RakutenPay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type47Enum)`](../../doc/models/type-47-enum.md) | Optional | **rakutenpay**<br><br>**Default**: `Type47Enum::RAKUTENPAY` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\RakutenPayBuilder;
use AdyenLib\Models\Type47Enum;

$rakutenPay = RakutenPayBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId2')
    ->recurringDetailReference('recurringDetailReference6')
    ->sdkData('sdkData4')
    ->storedPaymentMethodId('storedPaymentMethodId0')
    ->type(Type47Enum::RAKUTENPAY)
    ->build();
```

