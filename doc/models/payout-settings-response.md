
# Payout Settings Response

## Structure

`PayoutSettingsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(PayoutSettings[])`](../../doc/models/payout-settings.md) | Optional | The list of payout accounts. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutSettingsResponseBuilder;
use AdyenLib\Models\Builders\PayoutSettingsBuilder;
use AdyenLib\Models\PriorityEnum;
use AdyenLib\Models\VerificationStatus1Enum;

$payoutSettingsResponse = PayoutSettingsResponseBuilder::init()
    ->data(
        [
            PayoutSettingsBuilder::init(
                'id0',
                'transferInstrumentId8'
            )
                ->allowed(false)
                ->enabled(false)
                ->enabledFromDate('enabledFromDate2')
                ->priority(PriorityEnum::URGENT)
                ->verificationStatus(VerificationStatus1Enum::REJECTED)
                ->build(),
            PayoutSettingsBuilder::init(
                'id0',
                'transferInstrumentId8'
            )
                ->allowed(false)
                ->enabled(false)
                ->enabledFromDate('enabledFromDate2')
                ->priority(PriorityEnum::URGENT)
                ->verificationStatus(VerificationStatus1Enum::REJECTED)
                ->build()
        ]
    )
    ->build();
```

