
# Balance Webhook Setting Info Update

## Structure

`BalanceWebhookSettingInfoUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `conditions` | [`?(Condition[])`](../../doc/models/condition.md) | Optional | The array of conditions a balance change must meet for Adyen to send the webhook.<br><br>**Constraints**: *Minimum Items*: `0`, *Maximum Items*: `20` | getConditions(): ?array | setConditions(?array conditions): void |
| `currency` | `?string` | Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes) of the balance.<br><br>**Constraints**: *Minimum Length*: `1` | getCurrency(): ?string | setCurrency(?string currency): void |
| `status` | [`?string(Status6Enum)`](../../doc/models/status-6-enum.md) | Optional | The status of the webhook setting. Possible values:<br><br>* **active**: You receive a balance webhook if any of the conditions in this setting are met.<br>* **inactive**: You do not receive a balance webhook even if the conditions in this settings are met. | getStatus(): ?string | setStatus(?string status): void |
| `target` | [`?TargetUpdate2`](../../doc/models/target-update-2.md) | Optional | The type and ID of the resource about whose balance changes you want to be notified. | getTarget(): ?TargetUpdate2 | setTarget(?TargetUpdate2 target): void |
| `type` | [`?string(Type201Enum)`](../../doc/models/type-201-enum.md) | Optional | The type of the webhook you are configuring. Set to **balance**. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceWebhookSettingInfoUpdateBuilder;
use AdyenLib\Models\Builders\ConditionBuilder;
use AdyenLib\Models\BalanceTypeEnum;
use AdyenLib\Models\ConditionTypeEnum;
use AdyenLib\Models\Status6Enum;
use AdyenLib\Models\Builders\TargetUpdate2Builder;
use AdyenLib\Models\Type181Enum;
use AdyenLib\Models\Type201Enum;

$balanceWebhookSettingInfoUpdate = BalanceWebhookSettingInfoUpdateBuilder::init()
    ->conditions(
        [
            ConditionBuilder::init(
                BalanceTypeEnum::BALANCE,
                ConditionTypeEnum::LESSTHAN,
                214
            )->build(),
            ConditionBuilder::init(
                BalanceTypeEnum::BALANCE,
                ConditionTypeEnum::LESSTHAN,
                214
            )->build(),
            ConditionBuilder::init(
                BalanceTypeEnum::BALANCE,
                ConditionTypeEnum::LESSTHAN,
                214
            )->build()
        ]
    )
    ->currency('currency0')
    ->status(Status6Enum::ACTIVE)
    ->target(
        TargetUpdate2Builder::init()
            ->id('id2')
            ->type(Type181Enum::BALANCEACCOUNT)
            ->build()
    )
    ->type(Type201Enum::BALANCE)
    ->build();
```

