
# Balance Webhook Setting Info

## Structure

`BalanceWebhookSettingInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `conditions` | [`?(Condition[])`](../../doc/models/condition.md) | Optional | The array of conditions a balance change must meet for Adyen to send the webhook.<br><br>**Constraints**: *Minimum Items*: `0`, *Maximum Items*: `20` | getConditions(): ?array | setConditions(?array conditions): void |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes) of the balance.<br><br>**Constraints**: *Minimum Length*: `1` | getCurrency(): string | setCurrency(string currency): void |
| `status` | [`string(Status6Enum)`](../../doc/models/status-6-enum.md) | Required | The status of the webhook setting. Possible values:<br><br>* **active**: You receive a balance webhook if any of the conditions in this setting are met.<br>* **inactive**: You do not receive a balance webhook even if the conditions in this settings are met. | getStatus(): string | setStatus(string status): void |
| `target` | [`Target1`](../../doc/models/target-1.md) | Required | The type and ID of the resource about whose balance changes you want to be notified. | getTarget(): Target1 | setTarget(Target1 target): void |
| `type` | `string` | Required, Constant | The type of the webhook you are configuring. Set to **balance**.<br><br>**Value**: `'balance'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceWebhookSettingInfoBuilder;
use AdyenLib\Models\Status6Enum;
use AdyenLib\Models\Builders\Target1Builder;
use AdyenLib\Models\Type181Enum;
use AdyenLib\Models\Builders\ConditionBuilder;
use AdyenLib\Models\BalanceTypeEnum;
use AdyenLib\Models\ConditionTypeEnum;

$balanceWebhookSettingInfo = BalanceWebhookSettingInfoBuilder::init(
    'currency8',
    Status6Enum::ACTIVE,
    Target1Builder::init(
        'id2',
        Type181Enum::BALANCEACCOUNT
    )->build()
)
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
            )->build()
        ]
    )->build();
```

