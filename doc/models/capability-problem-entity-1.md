
# Capability Problem Entity 1

## Structure

`CapabilityProblemEntity1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documents` | `?(string[])` | Optional | List of document IDs corresponding to the verification errors from capabilities. | getDocuments(): ?array | setDocuments(?array documents): void |
| `id` | `?string` | Optional | - | getId(): ?string | setId(?string id): void |
| `owner` | [`?CapabilityProblemEntityRecursive1`](../../doc/models/capability-problem-entity-recursive-1.md) | Optional | - | getOwner(): ?CapabilityProblemEntityRecursive1 | setOwner(?CapabilityProblemEntityRecursive1 owner): void |
| `type` | [`?string(Type311Enum)`](../../doc/models/type-311-enum.md) | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\CapabilityProblemEntity1Builder;
use AdyenLib\Models\Builders\CapabilityProblemEntityRecursive1Builder;
use AdyenLib\Models\Type311Enum;

$capabilityProblemEntity1 = CapabilityProblemEntity1Builder::init()
    ->documents(
        [
            'documents5',
            'documents6',
            'documents7'
        ]
    )
    ->id('id6')
    ->owner(
        CapabilityProblemEntityRecursive1Builder::init()
            ->documents(
                [
                    'documents3',
                    'documents4'
                ]
            )
            ->id('id4')
            ->type(Type311Enum::LEGALENTITY)
            ->build()
    )
    ->type(Type311Enum::LEGALENTITY)
    ->build();
```

