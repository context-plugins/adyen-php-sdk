
# Lodging 2

[Lodging enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/lodging/) that may be required for processing the transaction and/or for interchange savings.

## Structure

`Lodging2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkInDate` | `?DateTime` | Optional | The check-in date.<br><br>* Min Length: 10 characters<br>* Max Length: 10 characters<br>* Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): yyyy-MM-dd<br>* **additionalData key:** `lodging.checkInDate` | getCheckInDate(): ?\DateTime | setCheckInDate(?\DateTime checkInDate): void |
| `checkOutDate` | `?DateTime` | Optional | The check-out date.<br><br>* Min Length: 10 characters<br>* Max Length: 10 characters<br>* Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): yyyy-MM-dd<br>* **additionalData key:** `lodging.checkOutDate` | getCheckOutDate(): ?\DateTime | setCheckOutDate(?\DateTime checkOutDate): void |
| `customerServicePhoneNumber` | `?string` | Optional | The toll-free phone number for the lodging customer service.<br><br>* Format: Alphanumeric<br>* For US and CA numbers must be 10 characters in length<br>* Must not start with a space<br>* Must not contain any special characters such as + or -<br>* Must not be all zeros.<br>* **additionalData key:** `lodging.customerServiceTollFreeNumber` | getCustomerServicePhoneNumber(): ?string | setCustomerServicePhoneNumber(?string customerServicePhoneNumber): void |
| `fireSafetyCompliance` | `?bool` | Optional | Indicates that the facility complies with the Hotel and Motel Fire Safety Act of 1990.<br><br>* **additionalData key:** `lodging.fireSafetyActIndicator` | getFireSafetyCompliance(): ?bool | setFireSafetyCompliance(?bool fireSafetyCompliance): void |
| `folio` | [`?Folio2`](../../doc/models/folio-2.md) | Optional | The folio information for the booking. | getFolio(): ?Folio2 | setFolio(?Folio2 folio): void |
| `foodBeverageCharges` | `?int` | Optional | Any charges for food and beverages associated with the booking, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `lodging.foodBeverageCharges` | getFoodBeverageCharges(): ?int | setFoodBeverageCharges(?int foodBeverageCharges): void |
| `lodgingChargeType` | [`?string(LodgingChargeTypeEnum)`](../../doc/models/lodging-charge-type-enum.md) | Optional | The category of lodging charges for the payment.<br><br>* **additionalData key:** `lodging.specialProgramCode` | getLodgingChargeType(): ?string | setLodgingChargeType(?string lodgingChargeType): void |
| `noShow` | `?bool` | Optional | Indicates if the customer didn't check in for their booking.<br><br>* **additionalData key:** `lodging.noShowIndicator` | getNoShow(): ?bool | setNoShow(?bool noShow): void |
| `prepaidExpenses` | `?int` | Optional | The prepaid expenses for the booking, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `lodging.prepaidExpenses` | getPrepaidExpenses(): ?int | setPrepaidExpenses(?int prepaidExpenses): void |
| `propertyPhoneNumber` | `?string` | Optional | The lodging property location's phone number.<br><br>* Format: Alphanumeric<br>* Min length: 10 characters<br>* For US and CA numbers must be 10 characters in length<br>* Must not start with a space<br>* Must not contain any special characters such as + or -<br>* Must not be all zeros.<br>* **additionalData key:** `lodging.propertyPhoneNumber` | getPropertyPhoneNumber(): ?string | setPropertyPhoneNumber(?string propertyPhoneNumber): void |
| `renterName` | `?string` | Optional | The name of the person renting the room.<br><br>* Format: ASCII<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `lodging.renterName` | getRenterName(): ?string | setRenterName(?string renterName): void |
| `rooms` | [`?(Room[])`](../../doc/models/room.md) | Optional | The list of rooms booked. | getRooms(): ?array | setRooms(?array rooms): void |
| `totalRoomTax` | `?int` | Optional | The total room tax amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `lodging.totalRoomTax` | getTotalRoomTax(): ?int | setTotalRoomTax(?int totalRoomTax): void |
| `totalTax` | `?int` | Optional | The total tax amount, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* **additionalData key:** `lodging.totalTax` | getTotalTax(): ?int | setTotalTax(?int totalTax): void |

## Example

```php
use AdyenLib\Models\Builders\Lodging2Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\Folio2Builder;

$lodging2 = Lodging2Builder::init()
    ->checkInDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->checkOutDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->customerServicePhoneNumber('customerServicePhoneNumber2')
    ->fireSafetyCompliance(false)
    ->folio(
        Folio2Builder::init()
            ->cashAdvances(122)
            ->number('number8')
            ->build()
    )
    ->build();
```

