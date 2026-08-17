
# Patchable Create Recurring Top Up

## Structure

`PatchableCreateRecurringTopUp`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Your description for the recurring top-up.<br><br>Maximum length is 140 characters. If you set a longer description, it will be cut off at 140 characters.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `140` | getDescription(): ?string | setDescription(?string description): void |
| `referenceForBeneficiary` | `?string` | Optional | A reference that is sent to the recipient. This reference is also sent in all webhooks related to the transfer, so you can use it to track statuses for both parties involved in the funds movement.<br><br>Supported characters: **a-z**, **A-Z**, **0-9**.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `80` | getReferenceForBeneficiary(): ?string | setReferenceForBeneficiary(?string referenceForBeneficiary): void |
| `status` | [`?string(Status6Enum)`](../../doc/models/status-6-enum.md) | Optional | The status of the recurring top-up. If not provided, by default, this is set to **active**.<br><br>Possible values:<br><br>* **active**:  the top up is enabled and funds will be pulled in.<br><br>* **inactive**: the top up is disabled and cannot be triggered. | getStatus(): ?string | setStatus(?string status): void |
| `topUpAmount` | [`?PatchableTopUpAmount2`](../../doc/models/patchable-top-up-amount-2.md) | Optional | The currency and value to be added to the balance account, specified in minor units. This can be a fixed amount or a target amount. | getTopUpAmount(): ?PatchableTopUpAmount2 | setTopUpAmount(?PatchableTopUpAmount2 topUpAmount): void |
| `trigger` | [`?PatchableTrigger2`](../../doc/models/patchable-trigger-2.md) | Optional | The condition that triggers the top-up. This can be a recurring schedule or a minimum balance threshold. | getTrigger(): ?PatchableTrigger2 | setTrigger(?PatchableTrigger2 trigger): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableCreateRecurringTopUpBuilder;
use AdyenLib\Models\Status6Enum;
use AdyenLib\Models\Builders\PatchableTopUpAmount2Builder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;
use AdyenLib\Models\Builders\PatchableTrigger2Builder;
use AdyenLib\Models\Builders\PatchableScheduleBuilder;
use AdyenLib\Models\ScheduleType1Enum;
use AdyenLib\Models\Builders\PatchableAmountDTO1Builder;

$patchableCreateRecurringTopUp = PatchableCreateRecurringTopUpBuilder::init()
    ->description('description0')
    ->referenceForBeneficiary('referenceForBeneficiary0')
    ->status(Status6Enum::ACTIVE)
    ->topUpAmount(
        PatchableTopUpAmount2Builder::init()
            ->fixed(
                PatchableAmountDTOBuilder::init()
                    ->currency('currency2')
                    ->value(164)
                    ->build()
            )
            ->target(
                PatchableAmountDTOBuilder::init()
                    ->currency('currency2')
                    ->value(164)
                    ->build()
            )
            ->build()
    )
    ->trigger(
        PatchableTrigger2Builder::init()
            ->schedule(
                PatchableScheduleBuilder::init()
                    ->type(ScheduleType1Enum::MONTHLY)
                    ->build()
            )
            ->threshold(
                PatchableAmountDTO1Builder::init()
                    ->currency('currency8')
                    ->value(32)
                    ->build()
            )
            ->build()
    )
    ->build();
```

