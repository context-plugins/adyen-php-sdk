
# MB Way

## Structure

`MBWay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `shopperEmail` | `string` | Required | - | getShopperEmail(): string | setShopperEmail(string shopperEmail): void |
| `telephoneNumber` | `string` | Required | - | getTelephoneNumber(): string | setTelephoneNumber(string telephoneNumber): void |
| `type` | [`?string(Type36Enum)`](../../doc/models/type-36-enum.md) | Optional | **mbway**<br><br>**Default**: `Type36Enum::MBWAY` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\MBWayBuilder;
use AdyenLib\Models\Type36Enum;

$mBWay = MBWayBuilder::init(
    'shopperEmail0',
    'telephoneNumber8'
)
    ->checkoutAttemptId('checkoutAttemptId2')
    ->sdkData('sdkData4')
    ->type(Type36Enum::MBWAY)
    ->build();
```

