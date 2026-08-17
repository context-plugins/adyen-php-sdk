
# Resource Reference 3

Contains information about the account holder associated with the `balanceAccount`.

## Structure

`ResourceReference3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The description of the resource. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the resource. | getId(): ?string | setId(?string id): void |
| `reference` | `?string` | Optional | The reference for the resource. | getReference(): ?string | setReference(?string reference): void |

## Example

```php
use AdyenLib\Models\Builders\ResourceReference3Builder;

$resourceReference3 = ResourceReference3Builder::init()
    ->description('description8')
    ->id('id8')
    ->reference('reference6')
    ->build();
```

