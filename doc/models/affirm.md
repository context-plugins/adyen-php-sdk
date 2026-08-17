
# Affirm

## Structure

`Affirm`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type1Enum)`](../../doc/models/type-1-enum.md) | Optional | **affirm**<br><br>**Default**: `Type1Enum::AFFIRM` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\AffirmBuilder;
use AdyenLib\Models\Type1Enum;

$affirm = AffirmBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId2')
    ->sdkData('sdkData4')
    ->type(Type1Enum::AFFIRM)
    ->build();
```

