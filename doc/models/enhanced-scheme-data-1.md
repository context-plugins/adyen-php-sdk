
# Enhanced Scheme Data 1

Enhanced scheme data that may be required for processing the payment. For example, airline information.

## Structure

`EnhancedSchemeData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `airline` | [`?Airline1`](../../doc/models/airline-1.md) | Optional | [Airline enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/airline/) that may be required for processing the transaction and/or for interchange savings. | getAirline(): ?Airline1 | setAirline(?Airline1 airline): void |
| `carRental` | [`?CarRental1`](../../doc/models/car-rental-1.md) | Optional | [Car rental enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/car-rental/) that may be required for processing the transaction and/or for interchange savings. | getCarRental(): ?CarRental1 | setCarRental(?CarRental1 carRental): void |
| `healthcare` | [`?Healthcare2`](../../doc/models/healthcare-2.md) | Optional | Healthcare auto-substantiation amounts for FSA/HSA card transactions. The amounts are used to qualify for reduced interchange rates on healthcare-eligible cards. | getHealthcare(): ?Healthcare2 | setHealthcare(?Healthcare2 healthcare): void |
| `levelTwoThree` | [`?LevelTwoThree2`](../../doc/models/level-two-three-2.md) | Optional | [Level 2 and Level 3 enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/l2-l3/) that may be required for processing the transaction and/or for interchange savings. | getLevelTwoThree(): ?LevelTwoThree2 | setLevelTwoThree(?LevelTwoThree2 levelTwoThree): void |
| `lodging` | [`?Lodging2`](../../doc/models/lodging-2.md) | Optional | [Lodging enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/lodging/) that may be required for processing the transaction and/or for interchange savings. | getLodging(): ?Lodging2 | setLodging(?Lodging2 lodging): void |
| `temporaryServices` | [`?TemporaryServices2`](../../doc/models/temporary-services-2.md) | Optional | [Temporary services enhanced scheme data](https://docs.adyen.com/payment-methods/cards/enhanced-scheme-data/temporary-services/) that may be required for processing the transaction and/or for interchange savings. | getTemporaryServices(): ?TemporaryServices2 | setTemporaryServices(?TemporaryServices2 temporaryServices): void |

## Example

```php
use AdyenLib\Models\Builders\EnhancedSchemeData1Builder;
use AdyenLib\Models\Builders\Airline1Builder;
use AdyenLib\Models\Builders\AgencyBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\CarRental1Builder;
use AdyenLib\Models\Builders\PickupInfoBuilder;
use AdyenLib\Models\RateTypeEnum;
use AdyenLib\Models\Builders\Healthcare2Builder;
use AdyenLib\Models\Builders\LevelTwoThree2Builder;
use AdyenLib\Models\Builders\Destination1Builder;
use AdyenLib\Models\Builders\ItemDetailLineBuilder;
use AdyenLib\Models\Builders\Lodging2Builder;
use AdyenLib\Models\Builders\Folio2Builder;

$enhancedSchemeData1 = EnhancedSchemeData1Builder::init()
    ->airline(
        Airline1Builder::init(
            'passengerName0'
        )
            ->agency(
                AgencyBuilder::init()
                    ->invoiceNumber('invoiceNumber6')
                    ->planName('planName6')
                    ->build()
            )
            ->boardingFee(160)
            ->code('code0')
            ->computerizedReservationSystem('computerizedReservationSystem4')
            ->customerReferenceNumber('customerReferenceNumber6')
            ->build()
    )
    ->carRental(
        CarRental1Builder::init(
            'renterName2'
        )
            ->customerServicePhoneNumber('customerServicePhoneNumber8')
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
            ->rentalAgreementNumber('rentalAgreementNumber4')
            ->build()
    )
    ->healthcare(
        Healthcare2Builder::init(
            16
        )
            ->dentalValue(132)
            ->otherMedicalValue(150)
            ->prescriptionValue(116)
            ->visionPrescriptionValue(166)
            ->build()
    )
    ->levelTwoThree(
        LevelTwoThree2Builder::init()
            ->customerReferenceNumber('customerReferenceNumber0')
            ->destination(
                Destination1Builder::init()
                    ->countryCode('countryCode0')
                    ->postalCode('postalCode6')
                    ->stateOrProvince('stateOrProvince2')
                    ->build()
            )
            ->dutyAmount(234)
            ->freightAmount(136)
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
            ->build()
    )
    ->lodging(
        Lodging2Builder::init()
            ->checkInDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->checkOutDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->customerServicePhoneNumber('customerServicePhoneNumber6')
            ->fireSafetyCompliance(false)
            ->folio(
                Folio2Builder::init()
                    ->cashAdvances(122)
                    ->number('number8')
                    ->build()
            )
            ->build()
    )
    ->build();
```

