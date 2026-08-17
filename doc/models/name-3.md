
# Name 3

## Structure

`Name3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `string` | Required | The individual's first name. Must not be blank. | getFirstName(): string | setFirstName(string firstName): void |
| `infix` | `?string` | Optional | The infix in the individual's name, if any. | getInfix(): ?string | setInfix(?string infix): void |
| `lastName` | `string` | Required | The individual's last name. Must not be blank. | getLastName(): string | setLastName(string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\Name3Builder;

$name3 = Name3Builder::init(
    'firstName0',
    'lastName8'
)
    ->infix('infix8')
    ->build();
```

