
# Name 2

The name of the shopper.

## Structure

`Name2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `string` | Required | The first name.<br><br>**Constraints**: *Maximum Length*: `80` | getFirstName(): string | setFirstName(string firstName): void |
| `lastName` | `string` | Required | The last name.<br><br>**Constraints**: *Maximum Length*: `80` | getLastName(): string | setLastName(string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\Name2Builder;

$name2 = Name2Builder::init(
    'firstName0',
    'lastName8'
)->build();
```

