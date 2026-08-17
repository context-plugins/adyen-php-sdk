
# Webhook Setting

## Structure

`WebhookSetting`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes) of the balance.<br><br>**Constraints**: *Minimum Length*: `1` | getCurrency(): string | setCurrency(string currency): void |
| `id` | `string` | Required | The unique identifier of the webhook setting. | getId(): string | setId(string id): void |
| `status` | `string` | Required | The status of the webhook setting. Possible values:<br><br>* **active**: You receive a balance webhook if any of the conditions in this setting are met.<br>* **inactive**: You do not receive a balance webhook even if the conditions in this settings are met. | getStatus(): string | setStatus(string status): void |
| `target` | [`Target3`](../../doc/models/target-3.md) | Required | The resource about whose balance change you want to get notified. | getTarget(): Target3 | setTarget(Target3 target): void |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\WebhookSettingBuilder;
use AdyenLib\Models\Builders\Target3Builder;
use AdyenLib\Models\Type181Enum;

$webhookSetting = WebhookSettingBuilder::init(
    'currency2',
    'id2',
    'status4',
    Target3Builder::init(
        'id2',
        Type181Enum::BALANCEACCOUNT
    )->build()
)
    ->type('WebhookSetting')
    ->build();
```

