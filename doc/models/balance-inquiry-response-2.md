
# Balance Inquiry Response 2

Content of the Balance Inquiry Response message.

## Structure

`BalanceInquiryResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `paymentAccountStatus` | [`?PaymentAccountStatus2`](../../doc/models/payment-account-status-2.md) | Optional | Data related to the result of a Balance Inquiry request.<br>If BalanceInquiryRequest. PaymentAccount present. | getPaymentAccountStatus(): ?PaymentAccountStatus2 | setPaymentAccountStatus(?PaymentAccountStatus2 paymentAccountStatus): void |
| `paymentReceipt` | [`?(PaymentReceipt[])`](../../doc/models/payment-receipt.md) | Optional | - | getPaymentReceipt(): ?array | setPaymentReceipt(?array paymentReceipt): void |

## Example

```php
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

$balanceInquiryResponse2 = BalanceInquiryResponse2Builder::init(
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

