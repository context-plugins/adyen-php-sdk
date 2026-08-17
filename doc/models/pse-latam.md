
# PSE Latam

## Structure

`PSELatam`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bank` | `string` | Required | The shopper's bank. | getBank(): string | setBank(string bank): void |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `clientType` | `string` | Required | The client type. | getClientType(): string | setClientType(string clientType): void |
| `identification` | `string` | Required | The identification code. | getIdentification(): string | setIdentification(string identification): void |
| `identificationType` | `string` | Required | The identification type. | getIdentificationType(): string | setIdentificationType(string identificationType): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type46Enum)`](../../doc/models/type-46-enum.md) | Optional | The payment method type. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\PSELatamBuilder;
use AdyenLib\Models\Type46Enum;

$pSELatam = PSELatamBuilder::init(
    'bank6',
    'clientType6',
    'identification4',
    'identificationType0'
)
    ->checkoutAttemptId('checkoutAttemptId4')
    ->sdkData('sdkData2')
    ->type(Type46Enum::PSE_PAYULATAM)
    ->build();
```

