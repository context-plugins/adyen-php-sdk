
# Resource Reference 1

Contains information about the balance account involved in the transfer.

## Structure

`ResourceReference1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The description of the resource. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the resource. | getId(): ?string | setId(?string id): void |
| `reference` | `?string` | Optional | The reference for the resource. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\ResourceReference1Builder;

$resourceReference1 = ResourceReference1Builder::init()
    ->description('description6')
    ->id('id6')
    ->reference('reference2')
    ->build();
```

