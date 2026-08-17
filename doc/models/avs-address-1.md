
# Avs Address 1

Contains the billing address of the card holder. The address details need to be AVS-compliant, which means that you need to provide at least street address.

## Structure

`AvsAddress1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `streetAddress` | `string` | Required | The street and house number of the address.<br><br>Example: 1 Infinite Loop, Cupertino. | getStreetAddress(): string | setStreetAddress(string streetAddress): void |
| `zip` | `?string` | Optional | The zip or post code of the address.<br><br>Example: CA 95014 | getZip(): ?string | setZip(?string zip): void |

## Example

```php
use AdyenLib\Models\Builders\AvsAddress1Builder;

$avsAddress1 = AvsAddress1Builder::init(
    'streetAddress6'
)
    ->zip('zip0')
    ->build();
```

