
# KYC Shareholder Check Result

## Structure

`KYCShareholderCheckResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checks` | [`?(KYCCheckStatusData[])`](../../doc/models/kyc-check-status-data.md) | Optional | A list of the checks and their statuses. | getChecks(): ?array | setChecks(?array checks): void |
| `legalArrangementCode` | `?string` | Optional | The unique ID of the legal arrangement to which the shareholder belongs, if applicable. | getLegalArrangementCode(): ?string | setLegalArrangementCode(?string legalArrangementCode): void |
| `legalArrangementEntityCode` | `?string` | Optional | The unique ID of the legal arrangement entity to which the shareholder belongs, if applicable. | getLegalArrangementEntityCode(): ?string | setLegalArrangementEntityCode(?string legalArrangementEntityCode): void |
| `shareholderCode` | `?string` | Optional | The code of the shareholder to which the check applies. | getShareholderCode(): ?string | setShareholderCode(?string shareholderCode): void |

## Example

```php
use AdyenLib\Models\Builders\KYCShareholderCheckResultBuilder;
use AdyenLib\Models\Builders\KYCCheckStatusDataBuilder;
use AdyenLib\Models\Status32Enum;
use AdyenLib\Models\Type211Enum;
use AdyenLib\Models\Builders\KYCCheckSummary2Builder;

$kYCShareholderCheckResult = KYCShareholderCheckResultBuilder::init()
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
    ->legalArrangementCode('legalArrangementCode2')
    ->legalArrangementEntityCode('legalArrangementEntityCode4')
    ->shareholderCode('shareholderCode8')
    ->build();
```

