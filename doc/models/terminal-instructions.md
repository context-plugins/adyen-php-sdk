
# Terminal Instructions

## Structure

`TerminalInstructions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adyenAppRestart` | `?bool` | Optional | Indicates whether the Adyen app on the payment terminal restarts automatically when the configuration is updated. | getAdyenAppRestart(): ?bool | setAdyenAppRestart(?bool adyenAppRestart): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalInstructionsBuilder;

$terminalInstructions = TerminalInstructionsBuilder::init()
    ->adyenAppRestart(false)
    ->build();
```

