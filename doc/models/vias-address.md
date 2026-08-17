
# Vias Address

## Structure

`ViasAddress`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | The name of the city. Required if the `houseNumberOrName`, `street`, `postalCode`, or `stateOrProvince` are provided. | getCity(): ?string | setCity(?string city): void |
| `country` | `string` | Required | The two-character country code of the address in ISO-3166-1 alpha-2 format. For example, **NL**. | getCountry(): string | setCountry(string country): void |
| `houseNumberOrName` | `?string` | Optional | The number or name of the house. | getHouseNumberOrName(): ?string | setHouseNumberOrName(?string houseNumberOrName): void |
| `postalCode` | `?string` | Optional | The postal code. Required if the `houseNumberOrName`, `street`, `city`, or `stateOrProvince` are provided.<br><br>Maximum length:<br><br>* 5 digits for addresses in the US.<br><br>* 10 characters for all other countries. | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `stateOrProvince` | `?string` | Optional | The abbreviation of the state or province. Required if the `houseNumberOrName`, `street`, `city`, or `postalCode` are provided.<br><br>Maximum length:<br><br>* 2 characters for addresses in the US or Canada.<br><br>* 3 characters for all other countries. | getStateOrProvince(): ?string | setStateOrProvince(?string stateOrProvince): void |
| `street` | `?string` | Optional | The name of the street. Required if the `houseNumberOrName`, `city`, `postalCode`, or `stateOrProvince` are provided. | getStreet(): ?string | setStreet(?string street): void |

## Example

```php
use AdyenLib\Models\Builders\ViasAddressBuilder;

$viasAddress = ViasAddressBuilder::init(
    'country2'
)
    ->city('city8')
    ->houseNumberOrName('houseNumberOrName6')
    ->postalCode('postalCode0')
    ->stateOrProvince('stateOrProvince6')
    ->street('street8')
    ->build();
```

