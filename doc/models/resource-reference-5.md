
# Resource Reference 5

The account holder associated with the balance account involved in the transfer.

## Structure

`ResourceReference5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The description of the resource. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the resource. | getId(): ?string | setId(?string id): void |
| `reference` | `?string` | Optional | The reference for the resource. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\ResourceReference5Builder;

$resourceReference5 = ResourceReference5Builder::init()
    ->description('description8')
    ->id('id2')
    ->reference('reference2')
    ->build();
```

