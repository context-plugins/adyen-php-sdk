
# Level Two Three 2

[Level 2 and Level 3 enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/l2-l3/) that may be required for processing the transaction and/or for interchange savings.

## Structure

`LevelTwoThree2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerReferenceNumber` | `?string` | Optional | The reference number to identify the customer and their order.<br><br>* Format: ASCII<br>* Max length: 25 characters<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `enhancedSchemeData.customerReference` | getCustomerReferenceNumber(): ?string | setCustomerReferenceNumber(?string customerReferenceNumber): void |
| `destination` | [`?Destination1`](../../doc/models/destination-1.md) | Optional | The destination address information. | getDestination(): ?Destination1 | setDestination(?Destination1 destination): void |
| `dutyAmount` | `?int` | Optional | The duty tax amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `enhancedSchemeData.dutyAmount` | getDutyAmount(): ?int | setDutyAmount(?int dutyAmount): void |
| `freightAmount` | `?int` | Optional | The shipping amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `enhancedSchemeData.freightAmount` | getFreightAmount(): ?int | setFreightAmount(?int freightAmount): void |
| `itemDetailLines` | [`?(ItemDetailLine[])`](../../doc/models/item-detail-line.md) | Optional | The list of item detail lines. | getItemDetailLines(): ?array | setItemDetailLines(?array itemDetailLines): void |
| `orderDate` | `?DateTime` | Optional | The date of the order.<br><br>* Min Length: 10 characters<br>* Max Length: 10 characters<br>* Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): yyyy-MM-dd<br>* **additionalData key:** `enhancedSchemeData.orderDate` | getOrderDate(): ?\DateTime | setOrderDate(?\DateTime orderDate): void |
| `shipFromPostalCode` | `?string` | Optional | The postal code of the address where the item is shipped from.<br><br>* Encoding: ASCII<br>* Max length: 10 characters<br>* For the US, it must be in five or nine digits format. For example, 10001 or 10001-0000.<br>* For Canada, it must be in 6 digits format. For example, M4B 1G5.<br>* **additionalData key:** `enhancedSchemeData.shipFromPostalCode` | getShipFromPostalCode(): ?string | setShipFromPostalCode(?string shipFromPostalCode): void |
| `totalTaxAmount` | `?int` | Optional | The amount of state or provincial [tax included in the total transaction amount](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/l2-l3#requirements-to-send-level-2-3-esd), in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* For L2 data: must not be all zeroes.<br>* For L3 data: can be zero.<br>* **additionalData key:** `enhancedSchemeData.totalTaxAmount` | getTotalTaxAmount(): ?int | setTotalTaxAmount(?int totalTaxAmount): void |

## Example

```php
use AdyenLib\Models\Builders\LevelTwoThree2Builder;
use AdyenLib\Models\Builders\Destination1Builder;
use AdyenLib\Models\Builders\ItemDetailLineBuilder;

$levelTwoThree2 = LevelTwoThree2Builder::init()
    ->customerReferenceNumber('customerReferenceNumber0')
    ->destination(
        Destination1Builder::init()
            ->countryCode('countryCode0')
            ->postalCode('postalCode6')
            ->stateOrProvince('stateOrProvince2')
            ->build()
    )
    ->dutyAmount(98)
    ->freightAmount(212)
    ->itemDetailLines(
        [
            ItemDetailLineBuilder::init()
                ->commodityCode('commodityCode4')
                ->description('description8')
                ->discountAmount(220)
                ->productCode('productCode0')
                ->quantity(184)
                ->build()
        ]
    )
    ->build();
```

