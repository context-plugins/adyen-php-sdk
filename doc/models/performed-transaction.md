
# Performed Transaction

## Structure

`PerformedTransaction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response1`](../../doc/models/response-1.md) | Required | Result of a message request processing.<br>If Result is Success, `ErrorCondition` is absent or not used in the processing of the message. In the other cases, the `ErrorCondition` has to be present and can refine the processing of the message response. `AdditionalResponse` gives more information about the success or the failure of the message request processing, for logging without real time involvements. | getResponse(): Response1 | setResponse(Response1 response): void |
| `saleData` | [`?SaleData`](../../doc/models/sale-data.md) | Optional | Data associated with the Sale System, with a particular value during the processing of the payment by the POI, including the cards acquisition. | getSaleData(): ?SaleData | setSaleData(?SaleData saleData): void |
| `pOIData` | [`?POIData`](../../doc/models/poi-data.md) | Optional | Data related to the POI System.<br>In the Message Response, identification of the POI transaction. | getPOIData(): ?POIData | setPOIData(?POIData pOIData): void |
| `paymentResult` | [`?PaymentResult1`](../../doc/models/payment-result-1.md) | Optional | - | getPaymentResult(): ?PaymentResult1 | setPaymentResult(?PaymentResult1 paymentResult): void |
| `loyaltyResult` | [`?(LoyaltyResult[])`](../../doc/models/loyalty-result.md) | Optional | - | getLoyaltyResult(): ?array | setLoyaltyResult(?array loyaltyResult): void |
| `reversedAmount` | `?float` | Optional | **Constraints**: `>= 0`, `<= 99999999.999999` | getReversedAmount(): ?float | setReversedAmount(?float reversedAmount): void |

## Example

```php
use AdyenLib\Models\Builders\PerformedTransactionBuilder;
use AdyenLib\Models\Builders\Response1Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\SaleDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\POIDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Models\Builders\PaymentResult1Builder;
use AdyenLib\Models\PaymentType1Enum;
use AdyenLib\Models\Builders\PaymentInstrumentDataBuilder;
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
use AdyenLib\Models\Builders\AmountsResp1Builder;
use AdyenLib\Models\Builders\Instalment1Builder;
use AdyenLib\Models\InstalmentTypeEnum;
use AdyenLib\Models\PeriodUnit1Enum;
use AdyenLib\Models\Builders\CurrencyConversionBuilder;
use AdyenLib\Models\Builders\ConvertedAmount1Builder;
use AdyenLib\Models\Builders\LoyaltyResultBuilder;
use AdyenLib\Models\Builders\LoyaltyAccount1Builder;
use AdyenLib\Models\Builders\LoyaltyAccountID2Builder;
use AdyenLib\Models\IdentificationSupport1Enum;
use AdyenLib\Models\Builders\LoyaltyAcquirerData1Builder;
use AdyenLib\Models\Builders\TransactionIDTypeBuilder;

$performedTransaction = PerformedTransactionBuilder::init(
    Response1Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)
    ->saleData(
        SaleDataBuilder::init(
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
            ->build()
    )
    ->pOIData(
        POIDataBuilder::init(
            TransactionIDType2Builder::init(
                'TransactionID2',
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
            )->build()
        )
            ->pOIReconciliationID(52)
            ->build()
    )
    ->paymentResult(
        PaymentResult1Builder::init()
            ->paymentType(PaymentType1Enum::ISSUERINSTALMENT)
            ->paymentInstrumentData(
                PaymentInstrumentDataBuilder::init(
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
            ->amountsResp(
                AmountsResp1Builder::init(
                    133.28
                )
                    ->currency('Currency0')
                    ->totalRebatesAmount(120.04)
                    ->totalFeesAmount(181.08)
                    ->cashBackAmount(206.58)
                    ->tipAmount(86.96)
                    ->build()
            )
            ->instalment(
                Instalment1Builder::init()
                    ->instalmentType(InstalmentTypeEnum::DEFERREDINSTALMENTS)
                    ->sequenceNumber(106)
                    ->planID('PlanID4')
                    ->period(70)
                    ->periodUnit(PeriodUnit1Enum::MONTHLY)
                    ->build()
            )
            ->currencyConversion(
                [
                    CurrencyConversionBuilder::init(
                        ConvertedAmount1Builder::init(
                            81.82,
                            'Currency0'
                        )->build()
                    )
                        ->customerApprovedFlag(false)
                        ->rate(175.8)
                        ->markup(100.86)
                        ->commission(197.78)
                        ->declaration('Declaration4')
                        ->build(),
                    CurrencyConversionBuilder::init(
                        ConvertedAmount1Builder::init(
                            81.82,
                            'Currency0'
                        )->build()
                    )
                        ->customerApprovedFlag(false)
                        ->rate(175.8)
                        ->markup(100.86)
                        ->commission(197.78)
                        ->declaration('Declaration4')
                        ->build()
                ]
            )
            ->build()
    )
    ->loyaltyResult(
        [
            LoyaltyResultBuilder::init(
                LoyaltyAccount1Builder::init(
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
            )
                ->currentBalance(171.12)
                ->loyaltyAcquirerData(
                    LoyaltyAcquirerData1Builder::init()
                        ->loyaltyAcquirerID('LoyaltyAcquirerID4')
                        ->approvalCode('ApprovalCode4')
                        ->loyaltyTransactionID(
                            TransactionIDTypeBuilder::init(
                                'TransactionID6',
                                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                            )->build()
                        )
                        ->hostReconciliationID('HostReconciliationID4')
                        ->build()
                )
                ->build(),
            LoyaltyResultBuilder::init(
                LoyaltyAccount1Builder::init(
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
            )
                ->currentBalance(171.12)
                ->loyaltyAcquirerData(
                    LoyaltyAcquirerData1Builder::init()
                        ->loyaltyAcquirerID('LoyaltyAcquirerID4')
                        ->approvalCode('ApprovalCode4')
                        ->loyaltyTransactionID(
                            TransactionIDTypeBuilder::init(
                                'TransactionID6',
                                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                            )->build()
                        )
                        ->hostReconciliationID('HostReconciliationID4')
                        ->build()
                )
                ->build()
        ]
    )
    ->reversedAmount(171.44)
    ->build();
```

