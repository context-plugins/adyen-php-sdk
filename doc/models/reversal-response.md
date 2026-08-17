
# Reversal Response

It conveys Information related to the reversal processed by the POI System.
Content of the Reversal Response message.

## Structure

`ReversalResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `pOIData` | [`?POIData4`](../../doc/models/poi-data-4.md) | Optional | Data related to the POI System.<br>If Result is Success. | getPOIData(): ?POIData4 | setPOIData(?POIData4 pOIData): void |
| `originalPOITransaction` | [`?OriginalPOITransaction`](../../doc/models/original-poi-transaction.md) | Optional | Identification of a previous POI transaction.<br>In the Payment Request message, it allows using the card of a previous CardAcquisition or Payment request. | getOriginalPOITransaction(): ?OriginalPOITransaction | setOriginalPOITransaction(?OriginalPOITransaction originalPOITransaction): void |
| `reversedAmount` | `?float` | Optional | Amount of the payment or loyalty to reverse.<br>Copy.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getReversedAmount(): ?float | setReversedAmount(?float reversedAmount): void |
| `paymentReceipt` | [`?(PaymentReceipt[])`](../../doc/models/payment-receipt.md) | Optional | - | getPaymentReceipt(): ?array | setPaymentReceipt(?array paymentReceipt): void |

## Example

```php
use AdyenLib\Models\Builders\ReversalResponseBuilder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\POIData4Builder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\OriginalPOITransactionBuilder;
use AdyenLib\Models\Builders\TransactionIDType4Builder;
use AdyenLib\Models\Builders\PaymentReceiptBuilder;
use AdyenLib\Models\DocumentQualifier1Enum;
use AdyenLib\Models\Builders\OutputContent1Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;

$reversalResponse = ReversalResponseBuilder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build()
)
    ->pOIData(
        POIData4Builder::init(
            TransactionIDType2Builder::init(
                'TransactionID2',
                DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
            )->build()
        )
            ->pOIReconciliationID(52)
            ->build()
    )
    ->originalPOITransaction(
        OriginalPOITransactionBuilder::init()
            ->saleID('SaleID6')
            ->pOIID('POIID0')
            ->pOITransactionID(
                TransactionIDType4Builder::init(
                    'TransactionID2',
                    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
                )->build()
            )
            ->reuseCardDataFlag(false)
            ->approvalCode('ApprovalCode0')
            ->build()
    )
    ->reversedAmount(161.34)
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

