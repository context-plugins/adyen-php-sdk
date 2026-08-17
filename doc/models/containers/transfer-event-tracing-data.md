
# Transfer Event Tracing Data

## Data Type

`UKFpsTracingData|USAchTracingData`

## Cases

| Type |
|  --- |
| [`UKFpsTracingData`](../../../doc/models/uk-fps-tracing-data.md) |
| [`USAchTracingData`](../../../doc/models/us-ach-tracing-data.md) |

## UKFpsTracingData

### Initialization Code

#### Example

```php
$value = UKFpsTracingDataBuilder::init(
    'fpid0'
)->build();
```

## USAchTracingData

### Initialization Code

#### Example

```php
$value = USAchTracingDataBuilder::init(
    'traceNumber8'
)->build();
```

