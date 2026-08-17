
# Card Acquisition Response 2

Content of the Card Acquisition Response message.

## Structure

`CardAcquisitionResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `saleData` | [`SaleData1`](../../doc/models/sale-data-1.md) | Required | Data related to the Sale System. | getSaleData(): SaleData1 | setSaleData(SaleData1 saleData): void |
| `pOIData` | [`POIData1`](../../doc/models/poi-data-1.md) | Required | Data related to the POI System. | getPOIData(): POIData1 | setPOIData(POIData1 pOIData): void |
| `paymentBrand` | `?(string[])` | Optional | Type of payment card.<br>Brands available for payment by the card and not chosen by the Customer.<br><br>**Constraints**: *Pattern*: `^.+$` | getPaymentBrand(): ?array | setPaymentBrand(?array paymentBrand): void |
| `paymentInstrumentData` | [`?PaymentInstrumentData1`](../../doc/models/payment-instrument-data-1.md) | Optional | Data related to the instrument of payment for the transaction.<br>If this type of payment card is configured to send information if the CardAcquisition response. | getPaymentInstrumentData(): ?PaymentInstrumentData1 | setPaymentInstrumentData(?PaymentInstrumentData1 paymentInstrumentData): void |
| `loyaltyAccount` | [`?(LoyaltyAccount[])`](../../doc/models/loyalty-account.md) | Optional | Data related to the loyalty System. | getLoyaltyAccount(): ?array | setLoyaltyAccount(?array loyaltyAccount): void |

## Example

```php
use AdyenLib\Models\Builders\CardAcquisitionResponse2Builder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\SaleData1Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\POIData1Builder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Models\Builders\PaymentInstrumentData1Builder;
use AdyenLib\Models\PaymentInstrumentType11Enum;
use AdyenLib\Models\Builders\CardData1Builder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\TrackFormat1Enum;
use AdyenLib\Models\Builders\CheckData1Builder;
use AdyenLib\Models\Builders\TrackData1Builder;
use AdyenLib\Models\Builders\MobileData1Builder;
use AdyenLib\Models\Builders\Geolocation1Builder;
use AdyenLib\Models\Builders\GeographicCoordinatesBuilder;
use AdyenLib\Models\Builders\UTMCoordinatesBuilder;
use AdyenLib\Models\Builders\StoredValueAccountIDBuilder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\Builders\LoyaltyAccountBuilder;
use AdyenLib\Models\Builders\LoyaltyAccountID2Builder;
use AdyenLib\Models\IdentificationSupport1Enum;

$cardAcquisitionResponse2 = CardAcquisitionResponse2Builder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build(),
    SaleData1Builder::init(
        TransactionIDType1Builder::init(
            'TransactionID2',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
        ->operatorID('OperatorID8')
        ->operatorLanguage('OperatorLanguage2')
        ->shiftNumber('ShiftNumber0')
        ->saleReferenceID('SaleReferenceID8')
        ->saleTerminalData(
            SaleTerminalData1Builder::init()
                ->totalsGroupID('TotalsGroupID4')
                ->build()
        )
        ->build(),
    POIData1Builder::init(
        TransactionIDType2Builder::init(
            'TransactionID2',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
        ->pOIReconciliationID(52)
        ->build()
)
    ->paymentBrand(
        [
            'PaymentBrand3',
            'PaymentBrand4'
        ]
    )
    ->paymentInstrumentData(
        PaymentInstrumentData1Builder::init(
            PaymentInstrumentType11Enum::CASH
        )
            ->protectedCardData('ProtectedCardData8')
            ->cardData(
                CardData1Builder::init()
                    ->paymentBrand('PaymentBrand0')
                    ->maskedPan('MaskedPan0')
                    ->paymentAccountRef('PaymentAccountRef8')
                    ->entryMode(
                        [
                            EntryModeEnum::MANUAL,
                            EntryModeEnum::KEYED
                        ]
                    )
                    ->cardCountryCode(3)
                    ->build()
            )
            ->checkData(
                CheckData1Builder::init()
                    ->bankID('BankID0')
                    ->accountNumber('AccountNumber6')
                    ->checkNumber('CheckNumber2')
                    ->trackData(
                        TrackData1Builder::init(
                            'TrackValue6'
                        )
                            ->trackNumb(3)
                            ->trackFormat(TrackFormat1Enum::JISII)
                            ->build()
                    )
                    ->checkCardNumber('CheckCardNumber6')
                    ->build()
            )
            ->mobileData(
                MobileData1Builder::init()
                    ->mobileCountryCode(3)
                    ->mobileNetworkCode(3)
                    ->maskedMSISDN(22)
                    ->geolocation(
                        Geolocation1Builder::init()
                            ->geographicCoordinates(
                                GeographicCoordinatesBuilder::init(
                                    'Latitude4',
                                    'Longitude2'
                                )->build()
                            )
                            ->uTMCoordinates(
                                UTMCoordinatesBuilder::init(
                                    'UTMZone6',
                                    'UTMEastward0',
                                    'UTMNorthward0'
                                )->build()
                            )->build()
                    )
                    ->protectedMobileData('ProtectedMobileData0')
                    ->build()
            )
            ->storedValueAccountID(
                StoredValueAccountIDBuilder::init(
                    StoredValueAccountType1Enum::PHONECARD,
                    [
                        EntryModeEnum::MAGSTRIPE,
                        EntryModeEnum::SCANNED
                    ],
                    IdentificationType11Enum::PHONENUMBER,
                    'StoredValueID8'
                )
                    ->storedValueProvider('StoredValueProvider4')
                    ->ownerName('OwnerName0')
                    ->expiryDate(4)
                    ->build()
            )
            ->build()
    )
    ->loyaltyAccount(
        [
            LoyaltyAccountBuilder::init(
                LoyaltyAccountID2Builder::init(
                    [
                        EntryModeEnum::FILE
                    ],
                    IdentificationType11Enum::ISOTRACK2,
                    'LoyaltyID4'
                )
                    ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
                    ->build()
            )
                ->loyaltyBrand('LoyaltyBrand0')
                ->build(),
            LoyaltyAccountBuilder::init(
                LoyaltyAccountID2Builder::init(
                    [
                        EntryModeEnum::FILE
                    ],
                    IdentificationType11Enum::ISOTRACK2,
                    'LoyaltyID4'
                )
                    ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
                    ->build()
            )
                ->loyaltyBrand('LoyaltyBrand0')
                ->build(),
            LoyaltyAccountBuilder::init(
                LoyaltyAccountID2Builder::init(
                    [
                        EntryModeEnum::FILE
                    ],
                    IdentificationType11Enum::ISOTRACK2,
                    'LoyaltyID4'
                )
                    ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
                    ->build()
            )
                ->loyaltyBrand('LoyaltyBrand0')
                ->build()
        ]
    )
    ->build();
```

