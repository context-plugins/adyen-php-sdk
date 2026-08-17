
# Create Recurring Top Up

## Structure

`CreateRecurringTopUp`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `counterparty` | [`TopUpCounterparty1`](../../doc/models/top-up-counterparty-1.md) | Required | The details about the counterparty that is funding the top-up. | getCounterparty(): TopUpCounterparty1 | setCounterparty(TopUpCounterparty1 counterparty): void |
| `description` | `string` | Required | Your description for the recurring top-up.<br><br>Maximum length is 140 characters. If you set a longer description, it will be cut off at 140 characters.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `140` | getDescription(): string | setDescription(string description): void |
| `referenceForBeneficiary` | `?string` | Optional | A reference that is sent to the recipient. This reference is also sent in all webhooks related to the transfer, so you can use it to track statuses for both parties involved in the funds movement.<br><br>Supported characters: **a-z**, **A-Z**, **0-9**.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `80` | getReferenceForBeneficiary(): ?string | setReferenceForBeneficiary(?string referenceForBeneficiary): void |
| `status` | [`?string(Status6Enum)`](../../doc/models/status-6-enum.md) | Optional | The status of the recurring top-up. If not provided, by default, this is set to **active**.<br><br>Possible values:<br><br>* **active**:  the top up is enabled and funds will be pulled in.<br><br>* **inactive**: the top up is disabled and cannot be triggered. | getStatus(): ?string | setStatus(?string status): void |
| `topUpAmount` | [`TopUpAmount1`](../../doc/models/top-up-amount-1.md) | Required | The currency and value to be added to the balance account, specified in minor units. This can be a fixed amount or a target amount. | getTopUpAmount(): TopUpAmount1 | setTopUpAmount(TopUpAmount1 topUpAmount): void |
| `trigger` | [`Trigger1`](../../doc/models/trigger-1.md) | Required | The condition that triggers the top-up. This can be a recurring schedule or a minimum balance threshold. | getTrigger(): Trigger1 | setTrigger(Trigger1 trigger): void |

## Example

```php
use AdyenLib\Models\Builders\CreateRecurringTopUpBuilder;
use AdyenLib\Models\Builders\TopUpCounterparty1Builder;
use AdyenLib\Models\Builders\TopUpAmount1Builder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\Trigger1Builder;
use AdyenLib\Models\Builders\Schedule21Builder;
use AdyenLib\Models\ScheduleType1Enum;
use AdyenLib\Models\Status6Enum;

$createRecurringTopUp = CreateRecurringTopUpBuilder::init(
    TopUpCounterparty1Builder::init(
        'transferInstrumentId4'
    )->build(),
    'description2',
    TopUpAmount1Builder::init()
        ->fixed(
            Amount17Builder::init(
                'currency0',
                164
            )->build()
        )
        ->target(
            Amount17Builder::init(
                'currency2',
                188
            )->build()
        )->build(),
    Trigger1Builder::init(
        Amount17Builder::init(
            'currency8',
            32
        )->build()
    )
        ->schedule(
            Schedule21Builder::init(
                ScheduleType1Enum::WEEKDAYS
            )->build()
        )->build()
)
    ->referenceForBeneficiary('referenceForBeneficiary8')
    ->status(Status6Enum::ACTIVE)
    ->build();
```

