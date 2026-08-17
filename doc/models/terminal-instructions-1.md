
# Terminal Instructions 1

Settings to define the behaviour of the payment terminal.

## Structure

`TerminalInstructions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adyenAppRestart` | `?bool` | Optional | Indicates whether the Adyen app on the payment terminal restarts automatically when the configuration is updated. | getAdyenAppRestart(): ?bool | setAdyenAppRestart(?bool adyenAppRestart): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalInstructions1Builder;

$terminalInstructions1 = TerminalInstructions1Builder::init()
    ->adyenAppRestart(false)
    ->build();
```

