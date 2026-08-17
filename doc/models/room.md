
# Room

## Structure

`Room`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `numberOfNights` | `?int` | Optional | The total number of nights the room is booked for.<br><br>* Format: Numeric<br>* Must be a number between 1 and 99<br>* **additionalData key:** `lodging.room[N].numberOfNights` | getNumberOfNights(): ?int | setNumberOfNights(?int numberOfNights): void |
| `rate` | `?int` | Optional | Room rate per night, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `lodging.room[N].rate` | getRate(): ?int | setRate(?int rate): void |

## Example

```php
use AdyenLib\Models\Builders\RoomBuilder;

$room = RoomBuilder::init()
    ->numberOfNights(138)
    ->rate(46)
    ->build();
```

