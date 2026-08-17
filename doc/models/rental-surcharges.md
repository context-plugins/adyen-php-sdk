
# Rental Surcharges

## Structure

`RentalSurcharges`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fuel` | `?int` | Optional | The fuel charges associated with the rental, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `carRental.fuelCharges` | getFuel(): ?int | setFuel(?int fuel): void |
| `insurance` | `?int` | Optional | Any insurance charges associated with the rental, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `carRental.insuranceCharges` | getInsurance(): ?int | setInsurance(?int insurance): void |
| `oneWayDropOff` | `?int` | Optional | The charge for not returning a car to the original rental location, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `carRental.oneWayDropOffCharges` | getOneWayDropOff(): ?int | setOneWayDropOff(?int oneWayDropOff): void |

## Example

```php
use AdyenLib\Models\Builders\RentalSurchargesBuilder;

$rentalSurcharges = RentalSurchargesBuilder::init()
    ->fuel(178)
    ->insurance(34)
    ->oneWayDropOff(110)
    ->build();
```

