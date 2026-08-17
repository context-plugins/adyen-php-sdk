
# Return Info

## Structure

`ReturnInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | The city where the car must be returned.<br><br>* Format: ASCII<br>* maxLength: 18 characters<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.returnCity` | getCity(): ?string | setCity(?string city): void |
| `countryCode` | `?string` | Optional | The country where the car must be returned, in [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) format.<br><br>* maxLength: 2 characters<br>* **additionalData key:** `carRental.returnCountry` | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `date` | `?DateTime` | Optional | The date by which the car must be returned.<br><br>* minLength: 10 characters<br>* maxLength: 10 characters<br>* Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): yyyy-MM-dd<br>* **additionalData key:** `carRental.returnDate` | getDate(): ?\DateTime | setDate(?\DateTime date): void |
| `locationId` | `?string` | Optional | The agency code, phone number, or address abbreviation.<br><br>* Format: ASCII<br>* maxLength: 10 characters<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.returnLocationId` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `stateOrProvince` | `?string` | Optional | The state or province where the car must be returned.<br><br>* Format: ASCII<br>* maxLength: 3 characters<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.returnStateProvince` | getStateOrProvince(): ?string | setStateOrProvince(?string stateOrProvince): void |

## Example

```php
use AdyenLib\Models\Builders\ReturnInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;

$returnInfo = ReturnInfoBuilder::init()
    ->city('city2')
    ->countryCode('countryCode8')
    ->date(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->locationId('locationId4')
    ->stateOrProvince('stateOrProvince0')
    ->build();
```

