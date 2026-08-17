
# Stored Payment Method 2

## Structure

`StoredPaymentMethod2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `issuer` | `string` | Required | The issuer id of the shopper's selected bank. | getIssuer(): string | setIssuer(string issuer): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`string(Type31Enum)`](../../doc/models/type-31-enum.md) | Required | **genericissuer** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\StoredPaymentMethod2Builder;
use AdyenLib\Models\Type31Enum;

$storedPaymentMethod2 = StoredPaymentMethod2Builder::init(
    'issuer0',
    Type31Enum::ONLINEBANKING_PL
)
    ->checkoutAttemptId('checkoutAttemptId6')
    ->recurringDetailReference('recurringDetailReference0')
    ->sdkData('sdkData0')
    ->storedPaymentMethodId('storedPaymentMethodId4')
    ->build();
```

