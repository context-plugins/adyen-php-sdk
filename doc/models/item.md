
# Item

The token requestor is an entity who requested tokenization of the card for secure payments.

## Structure

`Item`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The value to provide in the result. | getId(): ?string | setId(?string id): void |
| `name` | `?string` | Optional | The display name. | getName(): ?string | setName(?string name): void |

## Example

```php
use AdyenLib\Models\Builders\ItemBuilder;

$item = ItemBuilder::init()
    ->id('id2')
    ->name('name2')
    ->build();
```

