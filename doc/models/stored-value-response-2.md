
# Stored Value Response 2

Content of the Stored Value Response message.

## Structure

`StoredValueResponse2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `saleData` | [`SaleData1`](../../doc/models/sale-data-1.md) | Required | Data related to the Sale System. | getSaleData(): SaleData1 | setSaleData(SaleData1 saleData): void |
| `pOIData` | [`POIData1`](../../doc/models/poi-data-1.md) | Required | Data related to the POI System. | getPOIData(): POIData1 | setPOIData(POIData1 pOIData): void |
| `storedValueResult` | [`?(StoredValueResult[])`](../../doc/models/stored-value-result.md) | Optional | Result of loading/reloading a stored value card.<br>If StoredValueResponse.Result is Success or Partial, one entry per StoredValueRequest.StoredValueData loaded or activated. | getStoredValueResult(): ?array | setStoredValueResult(?array storedValueResult): void |
| `paymentReceipt` | [`?(PaymentReceipt[])`](../../doc/models/payment-receipt.md) | Optional | - | getPaymentReceipt(): ?array | setPaymentReceipt(?array paymentReceipt): void |

## Example

```php
use AdyenLib\Models\Builders\StoredValueResponse2Builder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\SaleData1Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;
use AdyenLib\Models\Builders\POIData1Builder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Models\Builders\StoredValueResultBuilder;
use AdyenLib\Models\StoredValueTransactionType2Enum;
use AdyenLib\Models\Builders\StoredValueAccountStatus1Builder;
use AdyenLib\Models\Builders\StoredValueAccountIDBuilder;
use AdyenLib\Models\StoredValueAccountType1Enum;
use AdyenLib\Models\EntryModeEnum;
use AdyenLib\Models\IdentificationType11Enum;
use AdyenLib\Models\Builders\PaymentReceiptBuilder;
use AdyenLib\Models\DocumentQualifier1Enum;
use AdyenLib\Models\Builders\OutputContent1Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;

$storedValueResponse2 = StoredValueResponse2Builder::init(
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
    ->storedValueResult(
        [
            StoredValueResultBuilder::init(
                StoredValueTransactionType2Enum::REVERSE
            )
                ->productCode(20)
                ->eanUpc(136)
                ->itemAmount(5.58)
                ->currency('Currency2')
                ->storedValueAccountStatus(
                    StoredValueAccountStatus1Builder::init(
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
                        ->currentBalance(45.56)
                        ->build()
                )
                ->build(),
            StoredValueResultBuilder::init(
                StoredValueTransactionType2Enum::REVERSE
            )
                ->productCode(20)
                ->eanUpc(136)
                ->itemAmount(5.58)
                ->currency('Currency2')
                ->storedValueAccountStatus(
                    StoredValueAccountStatus1Builder::init(
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
                        ->currentBalance(45.56)
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
                ->build()
        ]
    )
    ->build();
```

