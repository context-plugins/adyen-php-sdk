
# Mobile Pay

## Structure

`MobilePay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type37Enum)`](../../doc/models/type-37-enum.md) | Optional | **mobilepay**<br><br>**Default**: `Type37Enum::MOBILEPAY` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\MobilePayBuilder;
use AdyenLib\Models\Type37Enum;

$mobilePay = MobilePayBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId6')
    ->sdkData('sdkData0')
    ->type(Type37Enum::MOBILEPAY)
    ->build();
```

