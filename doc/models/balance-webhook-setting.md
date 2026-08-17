
# Balance Webhook Setting

## Structure

`BalanceWebhookSetting`

## Inherits From

[`WebhookSetting`](../../doc/models/webhook-setting.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `conditions` | [`?(Condition[])`](../../doc/models/condition.md) | Optional | The list of settings and criteria for triggering the [balance webhook](https://docs.adyen.com/api-explorer/balance-webhooks/latest/post/balanceAccount.balance.updated). | getConditions(): ?array | setConditions(?array conditions): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceWebhookSettingBuilder;
use AdyenLib\Models\Builders\Target3Builder;
use AdyenLib\Models\Type181Enum;
use AdyenLib\Models\Builders\ConditionBuilder;
use AdyenLib\Models\BalanceTypeEnum;
use AdyenLib\Models\ConditionTypeEnum;

$balanceWebhookSetting = BalanceWebhookSettingBuilder::init(
    'currency6',
    'id6',
    'status2',
    Target3Builder::init(
        'id2',
        Type181Enum::BALANCEACCOUNT
    )->build()
)
    ->type('balance')
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
    )->build();
```

