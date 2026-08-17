
# Capability Problem Entity Recursive

## Structure

`CapabilityProblemEntityRecursive`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documents` | `?(string[])` | Optional | List of document IDs to which the verification errors related to the capabilities correspond to. | getDocuments(): ?array | setDocuments(?array documents): void |
| `id` | `?string` | Optional | The ID of the entity. | getId(): ?string | setId(?string id): void |
| `type` | [`?string(Type33Enum)`](../../doc/models/type-33-enum.md) | Optional | Type of entity.<br><br>Possible values: **LegalEntity**, **BankAccount**, **Document**. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\CapabilityProblemEntityRecursiveBuilder;
use AdyenLib\Models\Type33Enum;

$capabilityProblemEntityRecursive = CapabilityProblemEntityRecursiveBuilder::init()
    ->documents(
        [
            'documents1'
        ]
    )
    ->id('id2')
    ->type(Type33Enum::BANKACCOUNT)
    ->build();
```

