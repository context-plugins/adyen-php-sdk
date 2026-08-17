
# KYC Check Status Data

## Structure

`KYCCheckStatusData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `requiredFields` | `?(string[])` | Optional | A list of the fields required for execution of the check. | getRequiredFields(): ?array | setRequiredFields(?array requiredFields): void |
| `status` | [`string(Status32Enum)`](../../doc/models/status-32-enum.md) | Required | The status of the check.<br><br>Possible values: **AWAITING_DATA** , **DATA_PROVIDED**, **FAILED**, **INVALID_DATA**, **PASSED**, **PENDING**, **RETRY_LIMIT_REACHED**. | getStatus(): string | setStatus(string status): void |
| `summary` | [`?KYCCheckSummary2`](../../doc/models/kyc-check-summary-2.md) | Optional | A summary of the execution of the check. | getSummary(): ?KYCCheckSummary2 | setSummary(?KYCCheckSummary2 summary): void |
| `type` | [`string(Type211Enum)`](../../doc/models/type-211-enum.md) | Required | The type of check.<br><br>Possible values:<br><br>* **BANK_ACCOUNT_VERIFICATION**: Used in v5 and earlier. Replaced by **PAYOUT_METHOD_VERIFICATION** in v6 and later.<br><br>* **COMPANY_VERIFICATION**<br><br>* **CARD_VERIFICATION**<br><br>* **IDENTITY_VERIFICATION**<br><br>* **LEGAL_ARRANGEMENT_VERIFICATION**<br><br>* **NONPROFIT_VERIFICATION**<br><br>* **PASSPORT_VERIFICATION**<br><br>* **PAYOUT_METHOD_VERIFICATION**: Used in v6 and later.<br><br>* **PCI_VERIFICATION** | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\KYCCheckStatusDataBuilder;
use AdyenLib\Models\Status32Enum;
use AdyenLib\Models\Type211Enum;
use AdyenLib\Models\Builders\KYCCheckSummary2Builder;

$kYCCheckStatusData = KYCCheckStatusDataBuilder::init(
    Status32Enum::PENDING_REVIEW,
    Type211Enum::BANK_ACCOUNT_VERIFICATION
)
    ->requiredFields(
        [
            'requiredFields6',
            'requiredFields7'
        ]
    )
    ->summary(
        KYCCheckSummary2Builder::init()
            ->kycCheckCode(128)
            ->kycCheckDescription('kycCheckDescription8')
            ->build()
    )
    ->build();
```

