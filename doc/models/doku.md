
# Doku

## Structure

`Doku`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `firstName` | `string` | Required | The shopper's first name. | getFirstName(): string | setFirstName(string firstName): void |
| `lastName` | `string` | Required | The shopper's last name. | getLastName(): string | setLastName(string lastName): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `shopperEmail` | `string` | Required | The shopper's email. | getShopperEmail(): string | setShopperEmail(string shopperEmail): void |
| `type` | [`string(Type23Enum)`](../../doc/models/type-23-enum.md) | Required | **doku** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\DokuBuilder;
use AdyenLib\Models\Type23Enum;

$doku = DokuBuilder::init(
    'firstName8',
    'lastName0',
    'shopperEmail0',
    Type23Enum::DOKU_OVO
)
    ->checkoutAttemptId('checkoutAttemptId2')
    ->sdkData('sdkData4')
    ->build();
```

