
# Pickup Info

## Structure

`PickupInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | The city where the car is rented.<br><br>* Format: ASCII<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.locationCity` | getCity(): ?string | setCity(?string city): void |
| `countryCode` | `?string` | Optional | The country where the car is rented, in [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) format.<br><br>* maxLength: 2 characters<br>* **additionalData key:** `carRental.locationCountry` | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `date` | `?DateTime` | Optional | The pick-up date.<br><br>* minLength: 10 characters<br>* maxLength: 10 characters<br>* Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): yyyy-MM-dd<br>* **additionalData key:** `carRental.checkOutDate` | getDate(): ?\DateTime | setDate(?\DateTime date): void |
| `stateOrProvince` | `?string` | Optional | The state or province where the car is rented.<br><br>* maxLength: 3 characters<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.locationStateProvince` | getStateOrProvince(): ?string | setStateOrProvince(?string stateOrProvince): void |

## Example

```php
use AdyenLib\Models\Builders\PickupInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;

$pickupInfo = PickupInfoBuilder::init()
    ->city('city4')
    ->countryCode('countryCode8')
    ->date(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->stateOrProvince('stateOrProvince4')
    ->build();
```

