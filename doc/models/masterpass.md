
# Masterpass

## Structure

`Masterpass`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `fundingSource` | [`?string(FundingSourceEnum)`](../../doc/models/funding-source-enum.md) | Optional | The funding source that should be used when multiple sources are available. For Brazilian combo cards, by default the funding source is credit. To use debit, set this value to **debit**. | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `masterpassTransactionId` | `string` | Required | The Masterpass transaction ID. | getMasterpassTransactionId(): string | setMasterpassTransactionId(string masterpassTransactionId): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type35Enum)`](../../doc/models/type-35-enum.md) | Optional | **masterpass**<br><br>**Default**: `Type35Enum::MASTERPASS` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\MasterpassBuilder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\Type35Enum;

$masterpass = MasterpassBuilder::init(
    'masterpassTransactionId6'
)
    ->checkoutAttemptId('checkoutAttemptId8')
    ->fundingSource(FundingSourceEnum::DEBIT)
    ->sdkData('sdkData8')
    ->type(Type35Enum::MASTERPASS)
    ->build();
```

