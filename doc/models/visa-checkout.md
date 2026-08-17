
# Visa Checkout

## Structure

`VisaCheckout`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `fundingSource` | [`?string(FundingSourceEnum)`](../../doc/models/funding-source-enum.md) | Optional | The funding source that should be used when multiple sources are available. For Brazilian combo cards, by default the funding source is credit. To use debit, set this value to **debit**. | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type55Enum)`](../../doc/models/type-55-enum.md) | Optional | **visacheckout**<br><br>**Default**: `Type55Enum::VISACHECKOUT` | getType(): ?string | setType(?string type): void |
| `visaCheckoutCallId` | `string` | Required | The Visa Click to Pay Call ID value. When your shopper selects a payment and/or a shipping address from Visa Click to Pay, you will receive a Visa Click to Pay Call ID. | getVisaCheckoutCallId(): string | setVisaCheckoutCallId(string visaCheckoutCallId): void |

## Example

```php
use AdyenLib\Models\Builders\VisaCheckoutBuilder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\Type55Enum;

$visaCheckout = VisaCheckoutBuilder::init(
    'visaCheckoutCallId8'
)
    ->checkoutAttemptId('checkoutAttemptId6')
    ->fundingSource(FundingSourceEnum::CREDIT)
    ->sdkData('sdkData0')
    ->type(Type55Enum::VISACHECKOUT)
    ->build();
```

