
# BLIK

## Structure

`BLIK`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `blikCode` | `?string` | Optional | BLIK code consisting of 6 digits. | getBlikCode(): ?string | setBlikCode(?string blikCode): void |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type13Enum)`](../../doc/models/type-13-enum.md) | Optional | **blik** | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\BLIKBuilder;

$bLIK = BLIKBuilder::init()
    ->blikCode('blikCode2')
    ->checkoutAttemptId('checkoutAttemptId0')
    ->recurringDetailReference('recurringDetailReference4')
    ->sdkData('sdkData4')
    ->storedPaymentMethodId('storedPaymentMethodId8')
    ->build();
```

