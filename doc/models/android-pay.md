
# Android Pay

## Structure

`AndroidPay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type6Enum)`](../../doc/models/type-6-enum.md) | Optional | **androidpay**<br><br>**Default**: `Type6Enum::ANDROIDPAY` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\AndroidPayBuilder;
use AdyenLib\Models\Type6Enum;

$androidPay = AndroidPayBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId0')
    ->sdkData('sdkData4')
    ->type(Type6Enum::ANDROIDPAY)
    ->build();
```

