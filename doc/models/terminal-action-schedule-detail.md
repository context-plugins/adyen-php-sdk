
# Terminal Action Schedule Detail

## Structure

`TerminalActionScheduleDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of the action on the specified terminal. | getId(): ?string | setId(?string id): void |
| `terminalId` | `?string` | Optional | The unique ID of the terminal that the action applies to. | getTerminalId(): ?string | setTerminalId(?string terminalId): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalActionScheduleDetailBuilder;

$terminalActionScheduleDetail = TerminalActionScheduleDetailBuilder::init()
    ->id('id6')
    ->terminalId('terminalId4')
    ->build();
```

