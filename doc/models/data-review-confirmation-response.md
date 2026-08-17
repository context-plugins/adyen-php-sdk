
# Data Review Confirmation Response

## Structure

`DataReviewConfirmationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dataReviewedAt` | `?string` | Optional | Date when data review was confirmed. | getDataReviewedAt(): ?string | setDataReviewedAt(?string dataReviewedAt): void |

## Example

```php
use AdyenLib\Models\Builders\DataReviewConfirmationResponseBuilder;

$dataReviewConfirmationResponse = DataReviewConfirmationResponseBuilder::init()
    ->dataReviewedAt('dataReviewedAt0')
    ->build();
```

