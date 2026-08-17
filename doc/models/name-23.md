
# Name 23

The individual's name.

## Structure

`Name23`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `string` | Required | The individual's first name. Must not be blank. | getFirstName(): string | setFirstName(string firstName): void |
| `infix` | `?string` | Optional | The infix in the individual's name, if any. | getInfix(): ?string | setInfix(?string infix): void |
| `lastName` | `string` | Required | The individual's last name. Must not be blank. | getLastName(): string | setLastName(string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\Name23Builder;

$name23 = Name23Builder::init(
    'firstName6',
    'lastName2'
)
    ->infix('infix2')
    ->build();
```

