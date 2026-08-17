
# Find Terminal Request

## Structure

`FindTerminalRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `terminal` | `string` | Required | The unique terminal ID in the format `[Device model]-[Serial number]`.<br><br>For example, **V400m-324689776**. | getTerminal(): string | setTerminal(string terminal): void |

## Example

```php
use AdyenLib\Models\Builders\FindTerminalRequestBuilder;

$findTerminalRequest = FindTerminalRequestBuilder::init(
    'terminal4'
)->build();
```

