
# KYC Payout Method Check Result

## Structure

`KYCPayoutMethodCheckResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checks` | [`?(KYCCheckStatusData[])`](../../doc/models/kyc-check-status-data.md) | Optional | A list of the checks and their statuses. | getChecks(): ?array | setChecks(?array checks): void |
| `payoutMethodCode` | `?string` | Optional | The unique ID of the payoput method to which the check applies. | getPayoutMethodCode(): ?string | setPayoutMethodCode(?string payoutMethodCode): void |

## Example

```php
use AdyenLib\Models\Builders\KYCPayoutMethodCheckResultBuilder;
use AdyenLib\Models\Builders\KYCCheckStatusDataBuilder;
use AdyenLib\Models\Status32Enum;
use AdyenLib\Models\Type211Enum;
use AdyenLib\Models\Builders\KYCCheckSummary2Builder;

$kYCPayoutMethodCheckResult = KYCPayoutMethodCheckResultBuilder::init()
    ->checks(
        [
            KYCCheckStatusDataBuilder::init(
                Status32Enum::INVALID_DATA,
                Type211Enum::PASSPORT_VERIFICATION
            )
                ->requiredFields(
                    [
                        'requiredFields0',
                        'requiredFields1'
                    ]
                )
                ->summary(
                    KYCCheckSummary2Builder::init()
                        ->kycCheckCode(128)
                        ->kycCheckDescription('kycCheckDescription8')
                        ->build()
                )
                ->build()
        ]
    )
    ->payoutMethodCode('payoutMethodCode6')
    ->build();
```

