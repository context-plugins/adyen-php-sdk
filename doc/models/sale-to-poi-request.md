
# Sale to POI Request

The SaleToPOIRequest message pair is a container for the request message content. It contains a MessageHeader and a message body.

## Structure

`SaleToPOIRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageHeader` | [`MessageHeader`](../../doc/models/message-header.md) | Required | Message header of the Sale to POI protocol message.<br>It conveys Information related to the Sale to POI protocol management. | getMessageHeader(): MessageHeader | setMessageHeader(MessageHeader messageHeader): void |
| `abortRequest` | [`?AbortRequest2`](../../doc/models/abort-request-2.md) | Optional | Content of the Abort Request message. | getAbortRequest(): ?AbortRequest2 | setAbortRequest(?AbortRequest2 abortRequest): void |
| `balanceInquiryRequest` | [`?BalanceInquiryRequest2`](../../doc/models/balance-inquiry-request-2.md) | Optional | Content of the Balance Inquiry Request message. | getBalanceInquiryRequest(): ?BalanceInquiryRequest2 | setBalanceInquiryRequest(?BalanceInquiryRequest2 balanceInquiryRequest): void |
| `cardAcquisitionRequest` | [`?CardAcquisitionRequest2`](../../doc/models/card-acquisition-request-2.md) | Optional | Content of the Card Acquisition Request message. | getCardAcquisitionRequest(): ?CardAcquisitionRequest2 | setCardAcquisitionRequest(?CardAcquisitionRequest2 cardAcquisitionRequest): void |
| `adminRequest` | [`?AdminRequest2`](../../doc/models/admin-request-2.md) | Optional | Content of the Admin Request message. | getAdminRequest(): ?AdminRequest2 | setAdminRequest(?AdminRequest2 adminRequest): void |
| `diagnosisRequest` | [`?DiagnosisRequest2`](../../doc/models/diagnosis-request-2.md) | Optional | Content of the Diagnosis Request message. | getDiagnosisRequest(): ?DiagnosisRequest2 | setDiagnosisRequest(?DiagnosisRequest2 diagnosisRequest): void |
| `displayRequest` | [`?DisplayRequest2`](../../doc/models/display-request-2.md) | Optional | Content of the Display Request message. | getDisplayRequest(): ?DisplayRequest2 | setDisplayRequest(?DisplayRequest2 displayRequest): void |
| `enableServiceRequest` | [`?EnableServiceRequest2`](../../doc/models/enable-service-request-2.md) | Optional | Content of the Enable Service Request message. | getEnableServiceRequest(): ?EnableServiceRequest2 | setEnableServiceRequest(?EnableServiceRequest2 enableServiceRequest): void |
| `eventNotification` | [`?EventNotification2`](../../doc/models/event-notification-2.md) | Optional | Content of the EventNotification message. | getEventNotification(): ?EventNotification2 | setEventNotification(?EventNotification2 eventNotification): void |
| `getTotalsRequest` | [`?GetTotalsRequest2`](../../doc/models/get-totals-request-2.md) | Optional | Content of the Get Totals Request message. | getGetTotalsRequest(): ?GetTotalsRequest2 | setGetTotalsRequest(?GetTotalsRequest2 getTotalsRequest): void |
| `inputRequest` | [`?InputRequest2`](../../doc/models/input-request-2.md) | Optional | Content of the Input Request message. | getInputRequest(): ?InputRequest2 | setInputRequest(?InputRequest2 inputRequest): void |
| `inputUpdate` | [`?InputUpdate2`](../../doc/models/input-update-2.md) | Optional | Content of the Input Update message. | getInputUpdate(): ?InputUpdate2 | setInputUpdate(?InputUpdate2 inputUpdate): void |
| `loginRequest` | [`?LoginRequest2`](../../doc/models/login-request-2.md) | Optional | Content of the Login Request message. | getLoginRequest(): ?LoginRequest2 | setLoginRequest(?LoginRequest2 loginRequest): void |
| `logoutRequest` | [`?LogoutRequest2`](../../doc/models/logout-request-2.md) | Optional | Content of the Logout Request message. | getLogoutRequest(): ?LogoutRequest2 | setLogoutRequest(?LogoutRequest2 logoutRequest): void |
| `paymentRequest` | [`?PaymentRequest21`](../../doc/models/payment-request-21.md) | Optional | Content of the Payment Request message. | getPaymentRequest(): ?PaymentRequest21 | setPaymentRequest(?PaymentRequest21 paymentRequest): void |
| `printRequest` | [`?PrintRequest2`](../../doc/models/print-request-2.md) | Optional | Content of the Print Request message. | getPrintRequest(): ?PrintRequest2 | setPrintRequest(?PrintRequest2 printRequest): void |
| `cardReaderAPDURequest` | [`?CardReaderAPDURequest2`](../../doc/models/card-reader-apdu-request-2.md) | Optional | Content of the Card Reader APDU Request message. | getCardReaderAPDURequest(): ?CardReaderAPDURequest2 | setCardReaderAPDURequest(?CardReaderAPDURequest2 cardReaderAPDURequest): void |
| `reconciliationRequest` | [`?ReconciliationRequest2`](../../doc/models/reconciliation-request-2.md) | Optional | Content of the Reconciliation Request message. | getReconciliationRequest(): ?ReconciliationRequest2 | setReconciliationRequest(?ReconciliationRequest2 reconciliationRequest): void |
| `reversalRequest` | [`?ReversalRequest2`](../../doc/models/reversal-request-2.md) | Optional | Content of the Reversal Request message. | getReversalRequest(): ?ReversalRequest2 | setReversalRequest(?ReversalRequest2 reversalRequest): void |
| `storedValueRequest` | [`?StoredValueRequest2`](../../doc/models/stored-value-request-2.md) | Optional | Content of the Stored Value Request message. | getStoredValueRequest(): ?StoredValueRequest2 | setStoredValueRequest(?StoredValueRequest2 storedValueRequest): void |
| `transactionStatusRequest` | [`?TransactionStatusRequest2`](../../doc/models/transaction-status-request-2.md) | Optional | Content of the TransactionStatus Request message. | getTransactionStatusRequest(): ?TransactionStatusRequest2 | setTransactionStatusRequest(?TransactionStatusRequest2 transactionStatusRequest): void |

## Example

```php
use AdyenLib\Models\Builders\SaleToPOIRequestBuilder;
use AdyenLib\Models\Builders\MessageHeaderBuilder;
use AdyenLib\Models\MessageClass1Enum;
use AdyenLib\Models\MessageCategory1Enum;
use AdyenLib\Models\MessageType1Enum;
use AdyenLib\Models\Builders\AbortRequest2Builder;
use AdyenLib\Models\Builders\MessageReference4Builder;
use AdyenLib\Models\MessageCategory2Enum;
use AdyenLib\Models\Builders\DisplayOutput1Builder;
use AdyenLib\Models\Device11Enum;
use AdyenLib\Models\InfoQualify1Enum;
use AdyenLib\Models\Builders\OutputContent1Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;
use AdyenLib\Models\Builders\MenuEntryBuilder;
use AdyenLib\Models\OutputFormat2Enum;
use AdyenLib\Models\MenuEntryTag1Enum;
use AdyenLib\Models\Builders\PredefinedContentBuilder;
use AdyenLib\Models\Builders\BalanceInquiryRequest2Builder;
use AdyenLib\Models\Builders\PaymentAccountReq2Builder;
use AdyenLib\Models\AccountType12Enum;
use AdyenLib\Models\Builders\TransactionIDTypeBuilder;
use AdyenLib\Utils\DateTimeHelper;
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
use AdyenLib\Models\Builders\LoyaltyAccountReq2Builder;
use AdyenLib\Models\Builders\LoyaltyAccountIDBuilder;
use AdyenLib\Models\IdentificationSupport1Enum;
use AdyenLib\Models\Builders\CardAcquisitionRequest2Builder;
use AdyenLib\Models\Builders\SaleData1Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\CardAcquisitionTransaction1Builder;
use AdyenLib\Models\LoyaltyHandling2Enum;
use AdyenLib\Models\ForceEntryModeEnum;
use AdyenLib\Models\Builders\AdminRequest2Builder;
use AdyenLib\Models\Builders\DiagnosisRequest2Builder;

$saleToPOIRequest = SaleToPOIRequestBuilder::init(
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
    ->abortRequest(
        AbortRequest2Builder::init(
            MessageReference4Builder::init()
                ->messageCategory(MessageCategory2Enum::PAYMENT)
                ->serviceID('ServiceID0')
                ->deviceID('DeviceID2')
                ->saleID('SaleID8')
                ->pOIID('POIID2')
                ->build(),
            'AbortReason6'
        )
            ->displayOutput(
                DisplayOutput1Builder::init(
                    Device11Enum::CASHIERDISPLAY,
                    InfoQualify1Enum::STATUS,
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
                    ->responseRequiredFlag(false)
                    ->minimumDisplayTime(110)
                    ->menuEntry(
                        [
                            MenuEntryBuilder::init(
                                OutputFormat2Enum::XHTML
                            )
                                ->menuEntryTag(MenuEntryTag1Enum::SUBMENU)
                                ->defaultSelectedFlag(false)
                                ->predefinedContent(
                                    PredefinedContentBuilder::init(
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
                                            ->build(),
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
                                ->outputXHTML('OutputXHTML8')
                                ->build(),
                            MenuEntryBuilder::init(
                                OutputFormat2Enum::XHTML
                            )
                                ->menuEntryTag(MenuEntryTag1Enum::SUBMENU)
                                ->defaultSelectedFlag(false)
                                ->predefinedContent(
                                    PredefinedContentBuilder::init(
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
                                            ->build(),
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
                                ->outputXHTML('OutputXHTML8')
                                ->build()
                        ]
                    )
                    ->outputSignature('OutputSignature4')
                    ->build()
            )
            ->build()
    )
    ->balanceInquiryRequest(
        BalanceInquiryRequest2Builder::init()
            ->paymentAccountReq(
                PaymentAccountReq2Builder::init()
                    ->accountType(AccountType12Enum::CHECKING)
                    ->cardAcquisitionReference(
                        TransactionIDTypeBuilder::init(
                            'TransactionID8',
                            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                        )->build()
                    )
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
                    ->build()
            )
            ->loyaltyAccountReq(
                LoyaltyAccountReq2Builder::init()
                    ->cardAcquisitionReference(
                        TransactionIDTypeBuilder::init(
                            'TransactionID8',
                            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                        )->build()
                    )
                    ->loyaltyAccountID(
                        LoyaltyAccountIDBuilder::init(
                            [
                                EntryModeEnum::FILE
                            ],
                            IdentificationType11Enum::ISOTRACK2,
                            'LoyaltyID4'
                        )
                            ->identificationSupport(IdentificationSupport1Enum::HYBRIDCARD)
                            ->build()
                    )
                    ->build()
            )
            ->build()
    )
    ->cardAcquisitionRequest(
        CardAcquisitionRequest2Builder::init(
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
            CardAcquisitionTransaction1Builder::init()
                ->allowedPaymentBrand(
                    [
                        'AllowedPaymentBrand6',
                        'AllowedPaymentBrand7'
                    ]
                )
                ->allowedLoyaltyBrand(
                    [
                        'AllowedLoyaltyBrand4'
                    ]
                )
                ->loyaltyHandling(LoyaltyHandling2Enum::PROCESSED)
                ->customerLanguage('CustomerLanguage8')
                ->forceEntryMode(
                    [
                        ForceEntryModeEnum::ICC
                    ]
                )
                ->build()
        )->build()
    )
    ->adminRequest(
        AdminRequest2Builder::init()
            ->serviceIdentification('ServiceIdentification0')
            ->build()
    )
    ->diagnosisRequest(
        DiagnosisRequest2Builder::init()
            ->pOIID('POIID2')
            ->hostDiagnosisFlag(false)
            ->acquirerID(
                [
                    48,
                    49,
                    50
                ]
            )
            ->build()
    )
    ->build();
```

