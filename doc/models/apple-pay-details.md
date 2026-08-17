
# Apple Pay Details

## Structure

`ApplePayDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `applePayToken` | `string` | Required | The stringified and base64 encoded `paymentData` you retrieved from the Apple framework.<br><br>**Constraints**: *Maximum Length*: `10000` | getApplePayToken(): string | setApplePayToken(string applePayToken): void |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `fundingSource` | [`?string(FundingSourceEnum)`](../../doc/models/funding-source-enum.md) | Optional | The funding source that should be used when multiple sources are available. For Brazilian combo cards, by default the funding source is credit. To use debit, set this value to **debit**. | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type7Enum)`](../../doc/models/type-7-enum.md) | Optional | **applepay**<br><br>**Default**: `Type7Enum::APPLEPAY` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\ApplePayDetailsBuilder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\Type7Enum;

$applePayDetails = ApplePayDetailsBuilder::init(
    'applePayToken8'
)
    ->checkoutAttemptId('checkoutAttemptId2')
    ->fundingSource(FundingSourceEnum::CREDIT)
    ->recurringDetailReference('recurringDetailReference6')
    ->sdkData('sdkData4')
    ->storedPaymentMethodId('storedPaymentMethodId0')
    ->type(Type7Enum::APPLEPAY)
    ->build();
```

