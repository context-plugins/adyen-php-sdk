
# Action 1

## Structure

`Action1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actionCode` | `string` | Required | The code identifying the action that needs to be completed. | getActionCode(): string | setActionCode(string actionCode): void |
| `resolved` | `bool` | Required | Indicates whether this action has been successfully completed. | getResolved(): bool | setResolved(bool resolved): void |

## Example

```php
use AdyenLib\Models\Builders\Action1Builder;

$action1 = Action1Builder::init(
    'actionCode2',
    false
)->build();
```

