
# Alma

## Structure

`Alma`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `feeType` | [`?string(FeeTypeEnum)`](../../doc/models/fee-type-enum.md) | Optional | **Alma payment request fee type** | getFeeType(): ?string | setFeeType(?string feeType): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type3Enum)`](../../doc/models/type-3-enum.md) | Optional | The payment method type. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\AlmaBuilder;
use AdyenLib\Models\FeeTypeEnum;
use AdyenLib\Models\Type3Enum;

$alma = AlmaBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId2')
    ->feeType(FeeTypeEnum::MERCHANTPAYS)
    ->sdkData('sdkData4')
    ->type(Type3Enum::ALMA)
    ->build();
```

