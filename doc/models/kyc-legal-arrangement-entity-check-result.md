
# KYC Legal Arrangement Entity Check Result

## Structure

`KYCLegalArrangementEntityCheckResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checks` | [`?(KYCCheckStatusData[])`](../../doc/models/kyc-check-status-data.md) | Optional | A list of the checks and their statuses. | getChecks(): ?array | setChecks(?array checks): void |
| `legalArrangementCode` | `?string` | Optional | The unique ID of the legal arrangement to which the entity belongs. | getLegalArrangementCode(): ?string | setLegalArrangementCode(?string legalArrangementCode): void |
| `legalArrangementEntityCode` | `?string` | Optional | The unique ID of the legal arrangement entity to which the check applies. | getLegalArrangementEntityCode(): ?string | setLegalArrangementEntityCode(?string legalArrangementEntityCode): void |

## Example

```php
use AdyenLib\Models\Builders\KYCLegalArrangementEntityCheckResultBuilder;
use AdyenLib\Models\Builders\KYCCheckStatusDataBuilder;
use AdyenLib\Models\Status32Enum;
use AdyenLib\Models\Type211Enum;
use AdyenLib\Models\Builders\KYCCheckSummary2Builder;

$kYCLegalArrangementEntityCheckResult = KYCLegalArrangementEntityCheckResultBuilder::init()
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
    ->legalArrangementCode('legalArrangementCode4')
    ->legalArrangementEntityCode('legalArrangementEntityCode6')
    ->build();
```

