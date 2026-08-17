
# Exchange Message

## Structure

`ExchangeMessage`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageCode` | `?string` | Optional | - | getMessageCode(): ?string | setMessageCode(?string messageCode): void |
| `messageDescription` | `?string` | Optional | - | getMessageDescription(): ?string | setMessageDescription(?string messageDescription): void |

## Example

```php
use AdyenLib\Models\Builders\ExchangeMessageBuilder;

$exchangeMessage = ExchangeMessageBuilder::init()
    ->messageCode('messageCode0')
    ->messageDescription('messageDescription6')
    ->build();
```

