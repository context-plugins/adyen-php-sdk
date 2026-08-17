
# Airline 11

Airline information.

## Structure

`Airline11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `legs` | [`?(Leg1[])`](../../doc/models/leg-1.md) | Optional | Details about the flight legs for this ticket. | getLegs(): ?array | setLegs(?array legs): void |
| `ticketNumber` | `?string` | Optional | The ticket's unique identifier | getTicketNumber(): ?string | setTicketNumber(?string ticketNumber): void |

## Example

```php
use AdyenLib\Models\Builders\Airline11Builder;
use AdyenLib\Models\Builders\Leg1Builder;

$airline11 = Airline11Builder::init()
    ->legs(
        [
            Leg1Builder::init()
                ->arrivalAirportCode('arrivalAirportCode8')
                ->basicFareCode('basicFareCode4')
                ->carrierCode('carrierCode6')
                ->departureAirportCode('departureAirportCode4')
                ->departureDate('departureDate8')
                ->build(),
            Leg1Builder::init()
                ->arrivalAirportCode('arrivalAirportCode8')
                ->basicFareCode('basicFareCode4')
                ->carrierCode('carrierCode6')
                ->departureAirportCode('departureAirportCode4')
                ->departureDate('departureDate8')
                ->build()
        ]
    )
    ->ticketNumber('ticketNumber8')
    ->build();
```

