
# D Barai

## Structure

`DBarai`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type20Enum)`](../../doc/models/type-20-enum.md) | Optional | **dbarai**<br><br>**Default**: `Type20Enum::DBARAI` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\DBaraiBuilder;
use AdyenLib\Models\Type20Enum;

$dBarai = DBaraiBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId8')
    ->recurringDetailReference('recurringDetailReference2')
    ->sdkData('sdkData2')
    ->storedPaymentMethodId('storedPaymentMethodId6')
    ->type(Type20Enum::DBARAI)
    ->build();
```

