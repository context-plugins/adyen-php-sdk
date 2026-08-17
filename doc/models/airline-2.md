
# Airline 2

## Structure

`Airline2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `legs` | [`?(Leg1[])`](../../doc/models/leg-1.md) | Optional | Details about the flight legs for this ticket. | getLegs(): ?array | setLegs(?array legs): void |
| `ticketNumber` | `?string` | Optional | The ticket's unique identifier | getTicketNumber(): ?string | setTicketNumber(?string ticketNumber): void |

## Example

```php
use AdyenLib\Models\Builders\Airline2Builder;
use AdyenLib\Models\Builders\Leg1Builder;

$airline2 = Airline2Builder::init()
    ->legs(
        [
            Leg1Builder::init()
                ->arrivalAirportCode('arrivalAirportCode8')
                ->basicFareCode('basicFareCode4')
                ->carrierCode('carrierCode6')
                ->departureAirportCode('departureAirportCode4')
                ->departureDate('departureDate8')
                ->build()
        ]
    )
    ->ticketNumber('ticketNumber4')
    ->build();
```

