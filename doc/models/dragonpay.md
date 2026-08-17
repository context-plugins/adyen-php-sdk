
# Dragonpay

## Structure

`Dragonpay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `issuer` | `string` | Required | The Dragonpay issuer value of the shopper's selected bank. Set this to an **id** of a Dragonpay issuer to preselect it. | getIssuer(): string | setIssuer(string issuer): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `shopperEmail` | `?string` | Optional | The shopper’s email address. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `type` | [`string(Type28Enum)`](../../doc/models/type-28-enum.md) | Required | **dragonpay** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\DragonpayBuilder;
use AdyenLib\Models\Type28Enum;

$dragonpay = DragonpayBuilder::init(
    'issuer0',
    Type28Enum::DRAGONPAY_OTC_NON_BANKING
)
    ->checkoutAttemptId('checkoutAttemptId6')
    ->sdkData('sdkData0')
    ->shopperEmail('shopperEmail4')
    ->build();
```

