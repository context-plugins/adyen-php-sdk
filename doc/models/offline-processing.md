
# Offline Processing

## Structure

`OfflineProcessing`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `chipFloorLimit` | `?int` | Optional | The maximum offline transaction amount for chip cards, in the processing currency and specified in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getChipFloorLimit(): ?int | setChipFloorLimit(?int chipFloorLimit): void |

## Example

```php
use AdyenLib\Models\Builders\OfflineProcessingBuilder;

$offlineProcessing = OfflineProcessingBuilder::init()
    ->chipFloorLimit(192)
    ->build();
```

