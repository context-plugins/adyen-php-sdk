
# Payment Response 21

Content of the Payment Response message.

## Structure

`PaymentResponse21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `saleData` | [`SaleData6`](../../doc/models/sale-data-6.md) | Required | Data related to the Sale System.<br>Copy. | getSaleData(): SaleData6 | setSaleData(SaleData6 saleData): void |
| `pOIData` | [`POIData1`](../../doc/models/poi-data-1.md) | Required | Data related to the POI System. | getPOIData(): POIData1 | setPOIData(POIData1 pOIData): void |
| `paymentResult` | [`?PaymentResult11`](../../doc/models/payment-result-11.md) | Optional | Data related to the result of a processed payment transaction.<br>If one data element is present. | getPaymentResult(): ?PaymentResult11 | setPaymentResult(?PaymentResult11 paymentResult): void |
| `loyaltyResult` | [`?(LoyaltyResult[])`](../../doc/models/loyalty-result.md) | Optional | Data related to the result of a processed loyalty transaction.<br>Loyalty cards used with the payment transaction. | getLoyaltyResult(): ?array | setLoyaltyResult(?array loyaltyResult): void |
| `paymentReceipt` | [`?(PaymentReceipt[])`](../../doc/models/payment-receipt.md) | Optional | Customer or Merchant payment receipt. If the payment receipts are printed by the Sale system and the POI or the Sale does not implement the Print exchange (Basic profile). | getPaymentReceipt(): ?array | setPaymentReceipt(?array paymentReceipt): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentResponse21Builder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\SaleData6Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\POIData1Builder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Models\Builders\PaymentResult11Builder;
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
use AdyenLib\Models\Builders\PaymentReceiptBuilder;
use AdyenLib\Models\DocumentQualifier1Enum;
use AdyenLib\Models\Builders\OutputContent1Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;

$paymentResponse21 = PaymentResponse21Builder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build(),
    SaleData6Builder::init(
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
    ->paymentResult(
        PaymentResult11Builder::init()
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
    ->paymentReceipt(
        [
            PaymentReceiptBuilder::init(
                DocumentQualifier1Enum::CUSTOMERRECEIPT,
                OutputContent1Builder::init(
                    OutputFormat1Enum::XHTML
                )
                    ->predefinedContent(
                        PredefinedContent1Builder::init(
                            'ReferenceID0'
                        )
                            ->language('Language2')
                            ->build()
                    )
                    ->outputText(
                        [
                            OutputTextBuilder::init(
                                'Text6'
                            )
                                ->characterSet(194)
                                ->startRow(74)
                                ->startColumn(220)
                                ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
                                ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
                                ->build()
                        ]
                    )
                    ->outputXHTML('OutputXHTML2')
                    ->outputBarcode(
                        OutputBarcode1Builder::init(
                            'BarcodeValue2'
                        )->build()
                    )->build()
            )
                ->integratedPrintFlag(false)
                ->requiredSignatureFlag(false)
                ->build(),
            PaymentReceiptBuilder::init(
                DocumentQualifier1Enum::CUSTOMERRECEIPT,
                OutputContent1Builder::init(
                    OutputFormat1Enum::XHTML
                )
                    ->predefinedContent(
                        PredefinedContent1Builder::init(
                            'ReferenceID0'
                        )
                            ->language('Language2')
                            ->build()
                    )
                    ->outputText(
                        [
                            OutputTextBuilder::init(
                                'Text6'
                            )
                                ->characterSet(194)
                                ->startRow(74)
                                ->startColumn(220)
                                ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
                                ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
                                ->build()
                        ]
                    )
                    ->outputXHTML('OutputXHTML2')
                    ->outputBarcode(
                        OutputBarcode1Builder::init(
                            'BarcodeValue2'
                        )->build()
                    )->build()
            )
                ->integratedPrintFlag(false)
                ->requiredSignatureFlag(false)
                ->build(),
            PaymentReceiptBuilder::init(
                DocumentQualifier1Enum::CUSTOMERRECEIPT,
                OutputContent1Builder::init(
                    OutputFormat1Enum::XHTML
                )
                    ->predefinedContent(
                        PredefinedContent1Builder::init(
                            'ReferenceID0'
                        )
                            ->language('Language2')
                            ->build()
                    )
                    ->outputText(
                        [
                            OutputTextBuilder::init(
                                'Text6'
                            )
                                ->characterSet(194)
                                ->startRow(74)
                                ->startColumn(220)
                                ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
                                ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
                                ->build()
                        ]
                    )
                    ->outputXHTML('OutputXHTML2')
                    ->outputBarcode(
                        OutputBarcode1Builder::init(
                            'BarcodeValue2'
                        )->build()
                    )->build()
            )
                ->integratedPrintFlag(false)
                ->requiredSignatureFlag(false)
                ->build()
        ]
    )
    ->build();
```

