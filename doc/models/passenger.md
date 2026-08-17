
# Passenger

## Structure

`Passenger`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateOfBirth` | `?DateTime` | Optional | The passenger's date of birth.<br><br>* Format `yyyy-MM-dd`<br>* minLength: 10<br>* maxLength: 10<br>* **additionalData key:** `airline.passenger[N].date_of_birth` | getDateOfBirth(): ?\DateTime | setDateOfBirth(?\DateTime dateOfBirth): void |
| `firstName` | `?string` | Optional | The passenger's first name.<br><br>> This field is required if the airline data includes passenger details or leg details.<br><br>* Encoding: ASCII<br>* **additionalData key:** `airline.passenger[N].first_name` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | The passenger's last name.<br><br>> This field is required if the airline data includes passenger details or leg details.<br><br>* Encoding: ASCII<br>* **additionalData key:** `airline.passenger[N].last_name` | getLastName(): ?string | setLastName(?string lastName): void |
| `phoneNumber` | `?string` | Optional | The passenger's phone number, including country code. This is an alphanumeric field that can include the '+' and '-' signs.<br><br>* Encoding: ASCII<br>* minLength: 3 characters<br>* maxLength: 30 characters<br>* **additionalData key:** `airline.passenger[N].phone_number` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `travellerType` | `?string` | Optional | The IATA passenger type code (PTC).<br><br>* Encoding: ASCII<br>* minLength: 3 characters<br>* maxLength: 6 characters<br>* **additionalData key:** `airline.passenger[N].traveller_type` | getTravellerType(): ?string | setTravellerType(?string travellerType): void |

## Example

```php
use AdyenLib\Models\Builders\PassengerBuilder;
use AdyenLib\Utils\DateTimeHelper;

$passenger = PassengerBuilder::init()
    ->dateOfBirth(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->firstName('firstName6')
    ->lastName('lastName4')
    ->phoneNumber('phoneNumber0')
    ->travellerType('travellerType8')
    ->build();
```

