
# Offline Processing 1

Settings for EMV [offline payment](https://docs.adyen.com/point-of-sale/offline-payments) features.

## Structure

`OfflineProcessing1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `chipFloorLimit` | `?int` | Optional | The maximum offline transaction amount for chip cards, in the processing currency and specified in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getChipFloorLimit(): ?int | setChipFloorLimit(?int chipFloorLimit): void |

## Example

```php
use AdyenLib\Models\Builders\OfflineProcessing1Builder;

$offlineProcessing1 = OfflineProcessing1Builder::init()
    ->chipFloorLimit(212)
    ->build();
```

