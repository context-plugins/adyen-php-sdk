
# KYC Ultimate Parent Company Check Result

## Structure

`KYCUltimateParentCompanyCheckResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checks` | [`?(KYCCheckStatusData[])`](../../doc/models/kyc-check-status-data.md) | Optional | A list of the checks and their statuses. | getChecks(): ?array | setChecks(?array checks): void |
| `ultimateParentCompanyCode` | `?string` | Optional | The code of the Ultimate Parent Company to which the check applies. | getUltimateParentCompanyCode(): ?string | setUltimateParentCompanyCode(?string ultimateParentCompanyCode): void |

## Example

```php
use AdyenLib\Models\Builders\KYCUltimateParentCompanyCheckResultBuilder;
use AdyenLib\Models\Builders\KYCCheckStatusDataBuilder;
use AdyenLib\Models\Status32Enum;
use AdyenLib\Models\Type211Enum;
use AdyenLib\Models\Builders\KYCCheckSummary2Builder;

$kYCUltimateParentCompanyCheckResult = KYCUltimateParentCompanyCheckResultBuilder::init()
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
                ->build()
        ]
    )
    ->ultimateParentCompanyCode('ultimateParentCompanyCode0')
    ->build();
```

