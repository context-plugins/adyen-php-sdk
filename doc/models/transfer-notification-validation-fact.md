
# Transfer Notification Validation Fact

## Structure

`TransferNotificationValidationFact`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `result` | `?string` | Optional | The evaluation result of the validation fact. | getResult(): ?string | setResult(?string result): void |
| `type` | `?string` | Optional | The type of the validation fact. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\TransferNotificationValidationFactBuilder;

$transferNotificationValidationFact = TransferNotificationValidationFactBuilder::init()
    ->result('result4')
    ->type('type8')
    ->build();
```

