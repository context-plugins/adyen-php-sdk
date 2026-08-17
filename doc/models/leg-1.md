
# Leg 1

## Structure

`Leg1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `arrivalAirportCode` | `?string` | Optional | The IATA 3-letter airport code of the destination airport. This field is required if the airline data includes leg details. | getArrivalAirportCode(): ?string | setArrivalAirportCode(?string arrivalAirportCode): void |
| `basicFareCode` | `?string` | Optional | The basic fare code for this leg. | getBasicFareCode(): ?string | setBasicFareCode(?string basicFareCode): void |
| `carrierCode` | `?string` | Optional | IATA code of the carrier operating the flight. | getCarrierCode(): ?string | setCarrierCode(?string carrierCode): void |
| `departureAirportCode` | `?string` | Optional | The IATA three-letter airport code of the departure airport. This field is required if the airline data includes leg details | getDepartureAirportCode(): ?string | setDepartureAirportCode(?string departureAirportCode): void |
| `departureDate` | `?string` | Optional | The flight departure date. | getDepartureDate(): ?string | setDepartureDate(?string departureDate): void |
| `flightNumber` | `?string` | Optional | The flight identifier. | getFlightNumber(): ?string | setFlightNumber(?string flightNumber): void |

## Example

```php
use AdyenLib\Models\Builders\Leg1Builder;

$leg1 = Leg1Builder::init()
    ->arrivalAirportCode('arrivalAirportCode8')
    ->basicFareCode('basicFareCode4')
    ->carrierCode('carrierCode6')
    ->departureAirportCode('departureAirportCode4')
    ->departureDate('departureDate8')
    ->build();
```

