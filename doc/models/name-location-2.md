
# Name Location 2

Contains the name and location of the merchant.

## Structure

`NameLocation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | The city where the merchant is located. | getCity(): ?string | setCity(?string city): void |
| `country` | `?string` | Optional | The country where the merchant is located in [three-letter country code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3) format. | getCountry(): ?string | setCountry(?string country): void |
| `countryOfOrigin` | `?string` | Optional | The home country in [three-digit country code](https://en.wikipedia.org/wiki/ISO_3166-1_numeric) format, used for government-controlled merchants such as embassies. | getCountryOfOrigin(): ?string | setCountryOfOrigin(?string countryOfOrigin): void |
| `name` | `?string` | Optional | The name of the merchant's shop or service. | getName(): ?string | setName(?string name): void |
| `rawData` | `?string` | Optional | The raw data. | getRawData(): ?string | setRawData(?string rawData): void |
| `state` | `?string` | Optional | The state where the merchant is located. | getState(): ?string | setState(?string state): void |

## Example

```php
use AdyenLib\Models\Builders\NameLocation2Builder;

$nameLocation2 = NameLocation2Builder::init()
    ->city('city6')
    ->country('country0')
    ->countryOfOrigin('countryOfOrigin2')
    ->name('name6')
    ->rawData('rawData2')
    ->build();
```

