
# MOL Pay

## Structure

`MOLPay`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `issuer` | `string` | Required | The shopper's bank. Specify this with the issuer value that corresponds to this bank. | getIssuer(): string | setIssuer(string issuer): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`string(Type38Enum)`](../../doc/models/type-38-enum.md) | Required | **molpay** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\MOLPayBuilder;
use AdyenLib\Models\Type38Enum;

$mOLPay = MOLPayBuilder::init(
    'issuer8',
    Type38Enum::MOLPAY_EBANKING_FPX_MY
)
    ->checkoutAttemptId('checkoutAttemptId4')
    ->sdkData('sdkData2')
    ->build();
```

