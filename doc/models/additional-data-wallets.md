
# Additional Data Wallets

## Structure

`AdditionalDataWallets`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `androidpayToken` | `?string` | Optional | The Android Pay token retrieved from the SDK. | getAndroidpayToken(): ?string | setAndroidpayToken(?string androidpayToken): void |
| `masterpassTransactionId` | `?string` | Optional | The Mastercard Masterpass Transaction ID retrieved from the SDK. | getMasterpassTransactionId(): ?string | setMasterpassTransactionId(?string masterpassTransactionId): void |
| `paymentToken` | `?string` | Optional | The Apple Pay token retrieved from the SDK. | getPaymentToken(): ?string | setPaymentToken(?string paymentToken): void |
| `paywithgoogleToken` | `?string` | Optional | The Google Pay token retrieved from the SDK. | getPaywithgoogleToken(): ?string | setPaywithgoogleToken(?string paywithgoogleToken): void |
| `samsungpayToken` | `?string` | Optional | The Samsung Pay token retrieved from the SDK. | getSamsungpayToken(): ?string | setSamsungpayToken(?string samsungpayToken): void |
| `visacheckoutCallId` | `?string` | Optional | The Visa Checkout Call ID retrieved from the SDK. | getVisacheckoutCallId(): ?string | setVisacheckoutCallId(?string visacheckoutCallId): void |

## Example

```php
use AdyenLib\Models\Builders\AdditionalDataWalletsBuilder;

$additionalDataWallets = AdditionalDataWalletsBuilder::init()
    ->androidpayToken('androidpay.token2')
    ->masterpassTransactionId('masterpass.transactionId2')
    ->paymentToken('payment.token4')
    ->paywithgoogleToken('paywithgoogle.token0')
    ->samsungpayToken('samsungpay.token0')
    ->build();
```

