
# Capability Problem Entity

## Structure

`CapabilityProblemEntity`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documents` | `?(string[])` | Optional | List of document IDs to which the verification errors related to the capabilities correspond to. | getDocuments(): ?array | setDocuments(?array documents): void |
| `id` | `?string` | Optional | The ID of the entity. | getId(): ?string | setId(?string id): void |
| `owner` | [`?CapabilityProblemEntityRecursive2`](../../doc/models/capability-problem-entity-recursive-2.md) | Optional | Contains details about the owner of the entity that has an error. | getOwner(): ?CapabilityProblemEntityRecursive2 | setOwner(?CapabilityProblemEntityRecursive2 owner): void |
| `type` | [`?string(Type33Enum)`](../../doc/models/type-33-enum.md) | Optional | Type of entity.<br><br>Possible values: **LegalEntity**, **BankAccount**, **Document**. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\CapabilityProblemEntityBuilder;
use AdyenLib\Models\Builders\CapabilityProblemEntityRecursive2Builder;
use AdyenLib\Models\Type33Enum;

$capabilityProblemEntity = CapabilityProblemEntityBuilder::init()
    ->documents(
        [
            'documents1'
        ]
    )
    ->id('id2')
    ->owner(
        CapabilityProblemEntityRecursive2Builder::init()
            ->documents(
                [
                    'documents3',
                    'documents4'
                ]
            )
            ->id('id4')
            ->type(Type33Enum::LEGALENTITY)
            ->build()
    )
    ->type(Type33Enum::BANKACCOUNT)
    ->build();
```

