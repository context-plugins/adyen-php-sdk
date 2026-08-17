
# Name 21

## Structure

`Name21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | The first name.<br><br>**Constraints**: *Maximum Length*: `80` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | The last name.<br><br>**Constraints**: *Maximum Length*: `80` | getLastName(): ?string | setLastName(?string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\Name21Builder;

$name21 = Name21Builder::init()
    ->firstName('firstName6')
    ->lastName('lastName2')
    ->build();
```

