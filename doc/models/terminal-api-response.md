
# Terminal API Response

The response payload of the Adyen Terminal API.

## Structure

`TerminalAPIResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `saleToPOIResponse` | [`SaleToPOIResponse`](../../doc/models/sale-to-poi-response.md) | Required | The SaleToPOIResponse message pair is a container for the response message content. It contains a MessageHeader and a message body. | getSaleToPOIResponse(): SaleToPOIResponse | setSaleToPOIResponse(SaleToPOIResponse saleToPOIResponse): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalAPIResponseBuilder;
use AdyenLib\Models\Builders\SaleToPOIResponseBuilder;
use AdyenLib\Models\Builders\MessageHeaderBuilder;
use AdyenLib\Models\MessageClass1Enum;
use AdyenLib\Models\MessageCategory1Enum;
use AdyenLib\Models\MessageType1Enum;
use AdyenLib\Models\Builders\BalanceInquiryResponse2Builder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\PaymentAccountStatus2Builder;
use AdyenLib\Models\Builders\PaymentInstrumentDataBuilder;
use AdyenLib\Models\PaymentInstrumentType11Enum;
use AdyenLib\Models\Builders\CardData1Builder;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\TrackFormat1Enum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\CheckData1Builder;
use AdyenLib\Models\Builders\TrackData1Builder;
use AdyenLib\Models\Builders\MobileData1Builder;
use AdyenLib\Models\Builders\Geolocation1Builder;
use AdyenLib\Models\Builders\GeographicCoordinatesBuilder;
use AdyenLib\Models\Builders\UTMCoordinatesBuilder;
use AdyenLib\Models\Builders\StoredValueAccountIDBuilder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\Builders\PaymentAcquirerDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType6Builder;
use AdyenLib\Models\Builders\PaymentReceiptBuilder;
use AdyenLib\Models\DocumentQualifier1Enum;
use AdyenLib\Models\Builders\OutputContent1Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;
use AdyenLib\Models\Builders\CardAcquisitionResponse2Builder;
use AdyenLib\Models\Builders\SaleData1Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\POIData1Builder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Models\Builders\PaymentInstrumentData1Builder;
use AdyenLib\Models\Builders\LoyaltyAccountBuilder;
use AdyenLib\Models\Builders\LoyaltyAccountID2Builder;
use AdyenLib\Models\IdentificationSupport1Enum;
use AdyenLib\Models\Builders\AdminResponse2Builder;
use AdyenLib\Models\Builders\DiagnosisResponse2Builder;
use AdyenLib\Models\Builders\POIStatus1Builder;
use AdyenLib\Models\GlobalStatus1Enum;
use AdyenLib\Models\PrinterStatus1Enum;
use AdyenLib\Models\Builders\HostStatusBuilder;
use AdyenLib\Models\Builders\DisplayResponse2Builder;
use AdyenLib\Models\Builders\OutputResultBuilder;
use AdyenLib\Models\Device3Enum;
use AdyenLib\Models\InfoQualify3Enum;

$terminalAPIResponse = TerminalAPIResponseBuilder::init(
    SaleToPOIResponseBuilder::init(
        MessageHeaderBuilder::init(
            MessageClass1Enum::SERVICE,
            MessageCategory1Enum::STOREDVALUE,
            MessageType1Enum::NOTIFICATION,
            'SaleID4',
            'POIID0'
        )
            ->protocolVersion('ProtocolVersion2')
            ->serviceID('ServiceID2')
            ->deviceID('DeviceID4')
            ->build()
    )
        ->balanceInquiryResponse(
            BalanceInquiryResponse2Builder::init(
                Response11Builder::init(
                    Result11Enum::PARTIAL
                )
                    ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
                    ->additionalResponse('AdditionalResponse8')
                    ->build()
            )
                ->paymentAccountStatus(
                    PaymentAccountStatus2Builder::init()
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
                        ->currentBalance(83.4)
                        ->currency('Currency4')
                        ->paymentAcquirerData(
                            PaymentAcquirerDataBuilder::init(
                                'MerchantID6',
                                'AcquirerPOIID4'
                            )
                                ->acquirerID(238)
                                ->acquirerTransactionID(
                                    TransactionIDType6Builder::init(
                                        'TransactionID2',
                                        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                                    )->build()
                                )
                                ->approvalCode('ApprovalCode8')
                                ->hostReconciliationID('HostReconciliationID8')
                                ->build()
                        )
                        ->build()
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
                            ->build()
                    ]
                )
                ->build()
        )
        ->cardAcquisitionResponse(
            CardAcquisitionResponse2Builder::init(
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
                        'PaymentBrand1',
                        'PaymentBrand2',
                        'PaymentBrand3'
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
                            ->build()
                    ]
                )
                ->build()
        )
        ->adminResponse(
            AdminResponse2Builder::init(
                Response11Builder::init(
                    Result11Enum::PARTIAL
                )
                    ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
                    ->additionalResponse('AdditionalResponse8')
                    ->build()
            )->build()
        )
        ->diagnosisResponse(
            DiagnosisResponse2Builder::init(
                Response11Builder::init(
                    Result11Enum::PARTIAL
                )
                    ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
                    ->additionalResponse('AdditionalResponse8')
                    ->build()
            )
                ->pOIStatus(
                    POIStatus1Builder::init(
                        GlobalStatus1Enum::MAINTENANCE
                    )
                        ->securityOKFlag(false)
                        ->pEDOKFlag(false)
                        ->cardReaderOKFlag(false)
                        ->printerStatus(PrinterStatus1Enum::PAPERLOW)
                        ->communicationOKFlag(false)
                        ->build()
                )
                ->hostStatus(
                    [
                        HostStatusBuilder::init(
                            120
                        )
                            ->isReachableFlag(false)
                            ->build(),
                        HostStatusBuilder::init(
                            120
                        )
                            ->isReachableFlag(false)
                            ->build()
                    ]
                )
                ->build()
        )
        ->displayResponse(
            DisplayResponse2Builder::init(
                [
                    OutputResultBuilder::init(
                        Device3Enum::CASHIERINPUT,
                        InfoQualify3Enum::DOCUMENT,
                        Response11Builder::init(
                            Result11Enum::PARTIAL
                        )
                            ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
                            ->additionalResponse('AdditionalResponse8')
                            ->build()
                    )->build(),
                    OutputResultBuilder::init(
                        Device3Enum::CASHIERINPUT,
                        InfoQualify3Enum::DOCUMENT,
                        Response11Builder::init(
                            Result11Enum::PARTIAL
                        )
                            ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
                            ->additionalResponse('AdditionalResponse8')
                            ->build()
                    )->build(),
                    OutputResultBuilder::init(
                        Device3Enum::CASHIERINPUT,
                        InfoQualify3Enum::DOCUMENT,
                        Response11Builder::init(
                            Result11Enum::PARTIAL
                        )
                            ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
                            ->additionalResponse('AdditionalResponse8')
                            ->build()
                    )->build()
                ]
            )->build()
        )->build()
)->build();
```

