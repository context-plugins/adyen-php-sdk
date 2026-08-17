
# We Chat Pay

## Structure

`WeChatPay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type56Enum)`](../../doc/models/type-56-enum.md) | Optional | **wechatpay**<br><br>**Default**: `Type56Enum::WECHATPAY` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\WeChatPayBuilder;
use AdyenLib\Models\Type56Enum;

$weChatPay = WeChatPayBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId4')
    ->sdkData('sdkData2')
    ->type(Type56Enum::WECHATPAY)
    ->build();
```

