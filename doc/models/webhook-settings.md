
# Webhook Settings

## Structure

`WebhookSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `webhookSettings` | [`?(WebhookSetting[])`](../../doc/models/webhook-setting.md) | Optional | The list of webhook settings. | getWebhookSettings(): ?array | setWebhookSettings(?array webhookSettings): void |

## Example

```php
use AdyenLib\Models\Builders\WebhookSettingsBuilder;
use AdyenLib\Models\Builders\WebhookSettingBuilder;
use AdyenLib\Models\Builders\Target3Builder;
use AdyenLib\Models\Type181Enum;

$webhookSettings = WebhookSettingsBuilder::init()
    ->webhookSettings(
        [
            WebhookSettingBuilder::init(
                'currency8',
                'id2',
                'status6',
                Target3Builder::init(
                    'id2',
                    Type181Enum::BALANCEACCOUNT
                )->build()
            )
                ->type('WebhookSetting')
                ->build(),
            WebhookSettingBuilder::init(
                'currency8',
                'id2',
                'status6',
                Target3Builder::init(
                    'id2',
                    Type181Enum::BALANCEACCOUNT
                )->build()
            )
                ->type('WebhookSetting')
                ->build()
        ]
    )
    ->build();
```

