
# Pay To

## Structure

`PayTo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `shopperAccountIdentifier` | `?string` | Optional | The shopper's banking details or payId reference, used to complete payment. | getShopperAccountIdentifier(): ?string | setShopperAccountIdentifier(?string shopperAccountIdentifier): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type41Enum)`](../../doc/models/type-41-enum.md) | Optional | **payto**<br><br>**Default**: `Type41Enum::PAYTO` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\PayToBuilder;
use AdyenLib\Models\Type41Enum;

$payTo = PayToBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId4')
    ->recurringDetailReference('recurringDetailReference8')
    ->sdkData('sdkData2')
    ->shopperAccountIdentifier('shopperAccountIdentifier8')
    ->storedPaymentMethodId('storedPaymentMethodId2')
    ->type(Type41Enum::PAYTO)
    ->build();
```

