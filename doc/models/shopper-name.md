
# Shopper Name

## Structure

`ShopperName`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `string` | Required | The first name.<br><br>**Constraints**: *Maximum Length*: `80` | getFirstName(): string | setFirstName(string firstName): void |
| `lastName` | `string` | Required | The last name.<br><br>**Constraints**: *Maximum Length*: `80` | getLastName(): string | setLastName(string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\ShopperNameBuilder;

$shopperName = ShopperNameBuilder::init(
    'firstName2',
    'lastName6'
)->build();
```

