
# Expiry 2

The expiration date of the card.

## Structure

`Expiry2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `month` | `?string` | Optional | The month in which the card will expire. | getMonth(): ?string | setMonth(?string month): void |
| `year` | `?string` | Optional | The year in which the card will expire. | getYear(): ?string | setYear(?string year): void |

## Example

```php
use AdyenLib\Models\Builders\Expiry2Builder;

$expiry2 = Expiry2Builder::init()
    ->month('month2')
    ->year('year6')
    ->build();
```

