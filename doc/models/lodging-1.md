
# Lodging 1

## Structure

`Lodging1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkInDate` | `?string` | Optional | The check-in date. | getCheckInDate(): ?string | setCheckInDate(?string checkInDate): void |
| `numberOfNights` | `?int` | Optional | The total number of nights the room is booked for. | getNumberOfNights(): ?int | setNumberOfNights(?int numberOfNights): void |

## Example

```php
use AdyenLib\Models\Builders\Lodging1Builder;

$lodging1 = Lodging1Builder::init()
    ->checkInDate('checkInDate0')
    ->numberOfNights(90)
    ->build();
```

