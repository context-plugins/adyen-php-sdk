
# Delivery Timeframe Enum

The estimated delivery time for the shopper to receive the goods.
Allowed values:

* `electronicDelivery`
* `sameDayShipping`
* `overnightShipping`
* `twoOrMoreDaysShipping`

## Enumeration

`DeliveryTimeframeEnum`

## Fields

| Name |
|  --- |
| `ELECTRONICDELIVERY` |
| `SAMEDAYSHIPPING` |
| `OVERNIGHTSHIPPING` |
| `TWOORMOREDAYSSHIPPING` |

## Example

```php
use AdyenLib\Models\DeliveryTimeframeEnum;

$deliveryTimeframe = DeliveryTimeframeEnum::ELECTRONICDELIVERY;
```

