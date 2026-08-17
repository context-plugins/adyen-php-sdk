
# We Chat Pay Mini Program

## Structure

`WeChatPayMiniProgram`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appId` | `?string` | Optional | - | getAppId(): ?string | setAppId(?string appId): void |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `openid` | `?string` | Optional | - | getOpenid(): ?string | setOpenid(?string openid): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type57Enum)`](../../doc/models/type-57-enum.md) | Optional | **wechatpayMiniProgram**<br><br>**Default**: `Type57Enum::WECHATPAYMINIPROGRAM` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\WeChatPayMiniProgramBuilder;
use AdyenLib\Models\Type57Enum;

$weChatPayMiniProgram = WeChatPayMiniProgramBuilder::init()
    ->appId('appId8')
    ->checkoutAttemptId('checkoutAttemptId8')
    ->openid('openid2')
    ->recurringDetailReference('recurringDetailReference2')
    ->sdkData('sdkData8')
    ->type(Type57Enum::WECHATPAYMINIPROGRAM)
    ->build();
```

