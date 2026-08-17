
# Bill Desk

## Structure

`BillDesk`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `issuer` | `string` | Required | The issuer id of the shopper's selected bank. | getIssuer(): string | setIssuer(string issuer): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`string(Type12Enum)`](../../doc/models/type-12-enum.md) | Required | **billdesk** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\BillDeskBuilder;
use AdyenLib\Models\Type12Enum;

$billDesk = BillDeskBuilder::init(
    'issuer0',
    Type12Enum::BILLDESK_ONLINE
)
    ->checkoutAttemptId('checkoutAttemptId6')
    ->sdkData('sdkData0')
    ->build();
```

