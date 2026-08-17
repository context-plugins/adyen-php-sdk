
# Identity 2

Contains the identity details of the party.

## Structure

`Identity2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fullLegalName` | `string` | Required | The complete legal name of the individual or entity. | getFullLegalName(): string | setFullLegalName(string fullLegalName): void |
| `name` | `string` | Required | A commonly used or human-readable name for the individual or entity. | getName(): string | setName(string name): void |

## Example

```php
use AdyenLib\Models\Builders\Identity2Builder;

$identity2 = Identity2Builder::init(
    'fullLegalName2',
    'name4'
)->build();
```

