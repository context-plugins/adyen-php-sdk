
# Capability Problem Entity Recursive 1

## Structure

`CapabilityProblemEntityRecursive1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documents` | `?(string[])` | Optional | List of document IDs corresponding to the verification errors from capabilities. | getDocuments(): ?array | setDocuments(?array documents): void |
| `id` | `?string` | Optional | - | getId(): ?string | setId(?string id): void |
| `type` | [`?string(Type311Enum)`](../../doc/models/type-311-enum.md) | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\CapabilityProblemEntityRecursive1Builder;
use AdyenLib\Models\Type311Enum;

$capabilityProblemEntityRecursive1 = CapabilityProblemEntityRecursive1Builder::init()
    ->documents(
        [
            'documents7',
            'documents8',
            'documents9'
        ]
    )
    ->id('id8')
    ->type(Type311Enum::BANKACCOUNT)
    ->build();
```

