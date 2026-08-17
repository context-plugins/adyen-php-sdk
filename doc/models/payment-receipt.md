
# Payment Receipt

Customer or Merchant payment receipt.
If the payment receipts are printed by the Sale system and the POI or the Sale does not implement the Print exchange (Basic profile).

## Structure

`PaymentReceipt`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documentQualifier` | [`string(DocumentQualifier1Enum)`](../../doc/models/document-qualifier-1-enum.md) | Required | Qualification of the document to print to the Cashier or the Customer.<br>SaleReceipt or CashierReceipt.<br>Possible values:<br><br>* **CashierReceipt**<br>* **CustomerReceipt**<br>* **Document**<br>* **Journal**<br>* **SaleReceipt**<br>* **Voucher** | getDocumentQualifier(): string | setDocumentQualifier(string documentQualifier): void |
| `integratedPrintFlag` | `?bool` | Optional | Type of the print integrated to other prints. | getIntegratedPrintFlag(): ?bool | setIntegratedPrintFlag(?bool integratedPrintFlag): void |
| `requiredSignatureFlag` | `?bool` | Optional | Indicate that the cardholder payment receipt requires a physical signature by the Customer.<br><br>**Default**: `false` | getRequiredSignatureFlag(): ?bool | setRequiredSignatureFlag(?bool requiredSignatureFlag): void |
| `outputContent` | [`OutputContent1`](../../doc/models/output-content-1.md) | Required | Content to display or print. | getOutputContent(): OutputContent1 | setOutputContent(OutputContent1 outputContent): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentReceiptBuilder;
use AdyenLib\Models\DocumentQualifier1Enum;
use AdyenLib\Models\Builders\OutputContent1Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;

$paymentReceipt = PaymentReceiptBuilder::init(
    DocumentQualifier1Enum::SALERECEIPT,
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
    ->build();
```

