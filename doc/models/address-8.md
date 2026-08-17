
# Address 8

## Structure

`Address8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | - | getCity(): ?string | setCity(?string city): void |
| `countryCode` | `?string` | Optional | - | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `postalCode` | `?string` | Optional | - | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `stateOrProvince` | `?string` | Optional | - | getStateOrProvince(): ?string | setStateOrProvince(?string stateOrProvince): void |
| `streetAddress` | `?string` | Optional | - | getStreetAddress(): ?string | setStreetAddress(?string streetAddress): void |
| `streetAddress2` | `?string` | Optional | - | getStreetAddress2(): ?string | setStreetAddress2(?string streetAddress2): void |

## Example

```php
use AdyenLib\Models\Builders\Address8Builder;

$address8 = Address8Builder::init()
    ->city('city6')
    ->countryCode('countryCode8')
    ->postalCode('postalCode2')
    ->stateOrProvince('stateOrProvince4')
    ->streetAddress('streetAddress6')
    ->build();
```

