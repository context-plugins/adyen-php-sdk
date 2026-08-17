
# Merchant Purchase Data

## Structure

`MerchantPurchaseData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `airline` | [`?Airline11`](../../doc/models/airline-11.md) | Optional | Airline information. | getAirline(): ?Airline11 | setAirline(?Airline11 airline): void |
| `lodging` | [`?(Lodging1[])`](../../doc/models/lodging-1.md) | Optional | Lodging information. | getLodging(): ?array | setLodging(?array lodging): void |
| `type` | `string` | Required, Constant | The type of events data.<br><br>Possible values:<br><br>- **merchantPurchaseData**: merchant purchase data<br><br>**Value**: `'merchantPurchaseData'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantPurchaseDataBuilder;
use AdyenLib\Models\Builders\Airline11Builder;
use AdyenLib\Models\Builders\Leg1Builder;
use AdyenLib\Models\Builders\Lodging1Builder;

$merchantPurchaseData = MerchantPurchaseDataBuilder::init()
    ->airline(
        Airline11Builder::init()
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
            ->ticketNumber('ticketNumber4')
            ->build()
    )
    ->lodging(
        [
            Lodging1Builder::init()
                ->checkInDate('checkInDate0')
                ->numberOfNights(50)
                ->build(),
            Lodging1Builder::init()
                ->checkInDate('checkInDate0')
                ->numberOfNights(50)
                ->build()
        ]
    )
    ->build();
```

