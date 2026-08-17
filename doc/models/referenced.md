
# Referenced

## Structure

`Referenced`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enableStandaloneRefunds` | `?bool` | Optional | Indicates whether referenced refunds are enabled on the standalone terminal. | getEnableStandaloneRefunds(): ?bool | setEnableStandaloneRefunds(?bool enableStandaloneRefunds): void |

## Example

```php
use AdyenLib\Models\Builders\ReferencedBuilder;

$referenced = ReferencedBuilder::init()
    ->enableStandaloneRefunds(false)
    ->build();
```

