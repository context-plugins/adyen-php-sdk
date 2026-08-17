
# Address 14

The address of the store.

## Structure

`Address14`

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
use AdyenLib\Models\Builders\Address14Builder;

$address14 = Address14Builder::init()
    ->city('city2')
    ->countryCode('countryCode2')
    ->postalCode('postalCode6')
    ->stateOrProvince('stateOrProvince0')
    ->streetAddress('streetAddress2')
    ->build();
```

