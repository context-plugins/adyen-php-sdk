
# Transfer Data Tracking

## Data Type

`ConfirmationTrackingData|EstimationTrackingData|InternalReviewTrackingData`

## Cases

| Type |
|  --- |
| [`ConfirmationTrackingData`](../../../doc/models/confirmation-tracking-data.md) |
| [`EstimationTrackingData`](../../../doc/models/estimation-tracking-data.md) |
| [`InternalReviewTrackingData`](../../../doc/models/internal-review-tracking-data.md) |

## ConfirmationTrackingData

### Initialization Code

#### Example

```php
$value = ConfirmationTrackingDataBuilder::init(
    Status15Enum::CREDITED
)->build();
```

## EstimationTrackingData

### Initialization Code

#### Example

```php
$value = EstimationTrackingDataBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
)->build();
```

## InternalReviewTrackingData

### Initialization Code

#### Example

```php
$value = InternalReviewTrackingDataBuilder::init(
    Status44Enum::PENDING
)->build();
```

