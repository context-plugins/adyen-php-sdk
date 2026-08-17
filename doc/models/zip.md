
# Zip

## Structure

`Zip`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `clickAndCollect` | `?string` | Optional | Set this to **true** if the shopper would like to pick up and collect their order, instead of having the goods delivered to them. | getClickAndCollect(): ?string | setClickAndCollect(?string clickAndCollect): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type58Enum)`](../../doc/models/type-58-enum.md) | Optional | **zip**<br><br>**Default**: `Type58Enum::ZIP` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\ZipBuilder;
use AdyenLib\Models\Type58Enum;

$zip = ZipBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId2')
    ->clickAndCollect('clickAndCollect6')
    ->recurringDetailReference('recurringDetailReference6')
    ->sdkData('sdkData4')
    ->storedPaymentMethodId('storedPaymentMethodId0')
    ->type(Type58Enum::ZIP)
    ->build();
```

