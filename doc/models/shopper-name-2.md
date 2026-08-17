
# Shopper Name 2

The shopper's full name.

## Structure

`ShopperName2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `string` | Required | The first name.<br><br>**Constraints**: *Maximum Length*: `80` | getFirstName(): string | setFirstName(string firstName): void |
| `lastName` | `string` | Required | The last name.<br><br>**Constraints**: *Maximum Length*: `80` | getLastName(): string | setLastName(string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\ShopperName2Builder;

$shopperName2 = ShopperName2Builder::init(
    'firstName4',
    'lastName4'
)->build();
```

