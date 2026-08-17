
# KYC Check Result 2

The results of the checks on the account holder.

## Structure

`KYCCheckResult2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checks` | [`?(KYCCheckStatusData[])`](../../doc/models/kyc-check-status-data.md) | Optional | A list of the checks and their statuses. | getChecks(): ?array | setChecks(?array checks): void |

## Example

```php
use AdyenLib\Models\Builders\KYCCheckResult2Builder;
use AdyenLib\Models\Builders\KYCCheckStatusDataBuilder;
use AdyenLib\Models\Status32Enum;
use AdyenLib\Models\Type211Enum;
use AdyenLib\Models\Builders\KYCCheckSummary2Builder;

$kYCCheckResult2 = KYCCheckResult2Builder::init()
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
                ->build(),
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
                ->build(),
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
    ->build();
```

