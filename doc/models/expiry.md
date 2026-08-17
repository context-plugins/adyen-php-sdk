
# Expiry

## Structure

`Expiry`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `month` | `?string` | Optional | The month in which the card will expire. | getMonth(): ?string | setMonth(?string month): void |
| `year` | `?string` | Optional | The year in which the card will expire. | getYear(): ?string | setYear(?string year): void |

## Example

```php
use AdyenLib\Models\Builders\ExpiryBuilder;

$expiry = ExpiryBuilder::init()
    ->month('month8')
    ->year('year0')
    ->build();
```

