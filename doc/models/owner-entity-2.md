
# Owner Entity 2

Contains information about the resource that owns the document.

## Structure

`OwnerEntity2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | Unique identifier of the resource that owns the document. For `type` **legalEntity**, this value is the unique identifier of the [legal entity](https://docs.adyen.com/api-explorer/legalentity/latest/post/legalEntities#responses-200-id). For `type` **bankAccount**, this value is the unique identifier of the [transfer instrument](https://docs.adyen.com/api-explorer/legalentity/latest/post/transferInstruments#responses-200-id). | getId(): string | setId(string id): void |
| `type` | `string` | Required | Type of resource that owns the document.<br><br>Possible values: **legalEntity**, **bankAccount**. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\OwnerEntity2Builder;

$ownerEntity2 = OwnerEntity2Builder::init(
    'id6',
    'type4'
)->build();
```

