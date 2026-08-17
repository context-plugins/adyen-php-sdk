
# Stored Payment Method 5

## Structure

`StoredPaymentMethod5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `deviceId` | `?string` | Optional | **Constraints**: *Maximum Length*: `36` | getDeviceId(): ?string | setDeviceId(?string deviceId): void |
| `issuer` | `?string` | Optional | - | getIssuer(): ?string | setIssuer(?string issuer): void |
| `recurringDetailReference` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token. | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `riskSignals` | [`?PixPayByBankRiskSignals`](../../doc/models/pix-pay-by-bank-risk-signals.md) | Optional | - | getRiskSignals(): ?PixPayByBankRiskSignals | setRiskSignals(?PixPayByBankRiskSignals riskSignals): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `storedPaymentMethodId` | `?string` | Optional | This is the `recurringDetailReference` returned in the response when you created the token.<br><br>**Constraints**: *Maximum Length*: `64` | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |
| `type` | [`?string(Type45Enum)`](../../doc/models/type-45-enum.md) | Optional | **paybybank_pix**<br><br>**Default**: `Type45Enum::PAYBYBANK_PIX` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\StoredPaymentMethod5Builder;
use AdyenLib\Models\Builders\PixPayByBankRiskSignalsBuilder;
use AdyenLib\Models\Builders\ConfidenceScoreBuilder;
use AdyenLib\Models\Type45Enum;

$storedPaymentMethod5 = StoredPaymentMethod5Builder::init()
    ->checkoutAttemptId('checkoutAttemptId6')
    ->deviceId('deviceId0')
    ->issuer('issuer0')
    ->recurringDetailReference('recurringDetailReference0')
    ->riskSignals(
        PixPayByBankRiskSignalsBuilder::init()
            ->confidenceScore(
                ConfidenceScoreBuilder::init()
                    ->errors(
                        [
                            'errors9',
                            'errors0',
                            'errors1'
                        ]
                    )
                    ->score(155.44)
                    ->build()
            )
            ->elapsedTimeSinceBoot(84)
            ->isRootedDevice(false)
            ->language('language0')
            ->osVersion('osVersion8')
            ->build()
    )
    ->type(Type45Enum::PAYBYBANK_PIX)
    ->build();
```

