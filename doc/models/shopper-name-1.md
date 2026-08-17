
# Shopper Name 1

The shopper's full name. This object is required for some payment methods such as AfterPay, Klarna, or if you're enrolled in the PayPal Seller Protection program.

## Structure

`ShopperName1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `string` | Required | The first name.<br><br>**Constraints**: *Maximum Length*: `80` | getFirstName(): string | setFirstName(string firstName): void |
| `lastName` | `string` | Required | The last name.<br><br>**Constraints**: *Maximum Length*: `80` | getLastName(): string | setLastName(string lastName): void |

## Example

```php
use AdyenLib\Models\Builders\ShopperName1Builder;

$shopperName1 = ShopperName1Builder::init(
    'firstName6',
    'lastName2'
)->build();
```

