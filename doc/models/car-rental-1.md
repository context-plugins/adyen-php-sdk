
# Car Rental 1

[Car rental enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/car-rental/) that may be required for processing the transaction and/or for interchange savings.

## Structure

`CarRental1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerServicePhoneNumber` | `?string` | Optional | The customer service phone number of the car rental company.<br><br>* Format: Alphanumeric<br>* maxLength: 17<br>* For US and CA numbers must be 10 characters in length<br>* Must not contain any special characters such as + or -<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.customerServiceTollFreeNumber` | getCustomerServicePhoneNumber(): ?string | setCustomerServicePhoneNumber(?string customerServicePhoneNumber): void |
| `noShow` | `?bool` | Optional | Indicates if the customer didn't pick up their rental car.<br><br>* **additionalData key:** `carRental.noShowIndicator` | getNoShow(): ?bool | setNoShow(?bool noShow): void |
| `pickupInfo` | [`?PickupInfo`](../../doc/models/pickup-info.md) | Optional | - | getPickupInfo(): ?PickupInfo | setPickupInfo(?PickupInfo pickupInfo): void |
| `rateType` | [`?string(RateTypeEnum)`](../../doc/models/rate-type-enum.md) | Optional | Indicates whether the rental rate is daily or weekly.<br><br>* **additionalData key:** `carRental.rateIndicator` | getRateType(): ?string | setRateType(?string rateType): void |
| `rentalAgreementNumber` | `?string` | Optional | The rental agreement number for the car rental.<br><br>* Format: ASCII<br>* maxLength: 9 characters<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.rentalAgreementNumber` | getRentalAgreementNumber(): ?string | setRentalAgreementNumber(?string rentalAgreementNumber): void |
| `rentalClassId` | `?string` | Optional | The classification of the rental car.<br><br>* Format: Alphanumeric<br>* maxLength: 4 characters<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.rentalClassId` | getRentalClassId(): ?string | setRentalClassId(?string rentalClassId): void |
| `rentalDays` | `?int` | Optional | The number of days the car is rented for.<br><br>* Format: Numeric<br>* Max value: 9999<br>* **additionalData key:** `carRental.daysRented` | getRentalDays(): ?int | setRentalDays(?int rentalDays): void |
| `rentalRate` | `?int` | Optional | Rental rate, in [minor units](https://docs.adyen.com/development-resources/currency-codes).<br><br>* For example, 2000 means USD 20.00.<br>* Encoding: Numeric<br>* Max value: 10000000000<br>* Frequency of the rental rate is specified in the rateType field.<br>* **additionalData key:** `carRental.rate` | getRentalRate(): ?int | setRentalRate(?int rentalRate): void |
| `rentalSurcharges` | [`?RentalSurcharges`](../../doc/models/rental-surcharges.md) | Optional | - | getRentalSurcharges(): ?RentalSurcharges | setRentalSurcharges(?RentalSurcharges rentalSurcharges): void |
| `renterName` | `string` | Required | The name of the person renting the car.<br><br>* Format: ASCII<br>* Must not start with a space or be all spaces.<br>* Must not be all zeros.<br>* **additionalData key:** `carRental.renterName` | getRenterName(): string | setRenterName(string renterName): void |
| `returnInfo` | [`?ReturnInfo`](../../doc/models/return-info.md) | Optional | - | getReturnInfo(): ?ReturnInfo | setReturnInfo(?ReturnInfo returnInfo): void |
| `taxExempt` | `?bool` | Optional | Indicates if the goods or services were tax-exempt, or if tax was not collected.<br><br>* **additionalData key:** `carRental.taxExemptIndicator` | getTaxExempt(): ?bool | setTaxExempt(?bool taxExempt): void |

## Example

```php
use AdyenLib\Models\Builders\CarRental1Builder;
use AdyenLib\Models\Builders\PickupInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\RateTypeEnum;

$carRental1 = CarRental1Builder::init(
    'renterName8'
)
    ->customerServicePhoneNumber('customerServicePhoneNumber4')
    ->noShow(false)
    ->pickupInfo(
        PickupInfoBuilder::init()
            ->city('city4')
            ->countryCode('countryCode8')
            ->date(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->stateOrProvince('stateOrProvince4')
            ->build()
    )
    ->rateType(RateTypeEnum::DAILY)
    ->rentalAgreementNumber('rentalAgreementNumber0')
    ->build();
```

