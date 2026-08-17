
# Google Pay Donations

## Structure

`GooglePayDonations`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `fundingSource` | [`?string(FundingSourceEnum)`](../../doc/models/funding-source-enum.md) | Optional | The funding source that should be used when multiple sources are available. For Brazilian combo cards, by default the funding source is credit. To use debit, set this value to **debit**. | getFundingSource(): ?string | setFundingSource(?string fundingSource): void |
| `googlePayCardNetwork` | `?string` | Optional | The selected payment card network. | getGooglePayCardNetwork(): ?string | setGooglePayCardNetwork(?string googlePayCardNetwork): void |
| `googlePayToken` | `string` | Required | The `token` that you obtained from the [Google Pay API](https://developers.google.com/pay/api/web/reference/response-objects#PaymentData) `PaymentData` response.<br><br>**Constraints**: *Maximum Length*: `10000` | getGooglePayToken(): string | setGooglePayToken(string googlePayToken): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `threeDS2SdkVersion` | `?string` | Optional | Required for mobile integrations. Version of the 3D Secure 2 mobile SDK.<br><br>**Constraints**: *Maximum Length*: `12` | getThreeDS2SdkVersion(): ?string | setThreeDS2SdkVersion(?string threeDS2SdkVersion): void |
| `type` | [`?string(Type24Enum)`](../../doc/models/type-24-enum.md) | Optional | **googlepay**, **paywithgoogle**<br><br>**Default**: `Type24Enum::GOOGLEPAY` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\GooglePayDonationsBuilder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\Type24Enum;

$googlePayDonations = GooglePayDonationsBuilder::init(
    'googlePayToken2'
)
    ->checkoutAttemptId('checkoutAttemptId6')
    ->fundingSource(FundingSourceEnum::DEBIT)
    ->googlePayCardNetwork('googlePayCardNetwork6')
    ->recurringDetailReference('recurringDetailReference0')
    ->sdkData('sdkData0')
    ->type(Type24Enum::GOOGLEPAY)
    ->build();
```

