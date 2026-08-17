
# Print Output

## Structure

`PrintOutput`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `documentQualifier` | [`string(DocumentQualifier2Enum)`](../../doc/models/document-qualifier-2-enum.md) | Required | Qualification of the document to print to the Cashier or the Customer. Allows the manager of the printer, Sale or POI Terminal, to send information to a physical printer or to use the paper type accordingly.<br>Possible values:<br><br>* **CashierReceipt**<br>* **CustomerReceipt**<br>* **Document**<br>* **Journal**<br>* **SaleReceipt**<br>* **Voucher** | getDocumentQualifier(): string | setDocumentQualifier(string documentQualifier): void |
| `responseMode` | [`string(ResponseMode1Enum)`](../../doc/models/response-mode-1-enum.md) | Required | Message response awaited by the initiator of the Request. Allows various types and synchronisation of requests for Print or Sound.<br>Possible values:<br><br>* **Immediate**<br>* **NotRequired**<br>* **PrintEnd**<br>* **SoundEnd** | getResponseMode(): string | setResponseMode(string responseMode): void |
| `integratedPrintFlag` | `?bool` | Optional | Type of the print integrated in other prints. Allows a separated printing (paper cut if available), or integration with the sale receipt or other print. If the printing is integrated, the response is always immediate, even if the `ResponseMode` is set to `PrintEnd`.<br><br>**Default**: `false` | getIntegratedPrintFlag(): ?bool | setIntegratedPrintFlag(?bool integratedPrintFlag): void |
| `requiredSignatureFlag` | `?bool` | Optional | Indicates that the cardholder payment receipt requires a physical signature by the Customer.<br><br>**Default**: `false` | getRequiredSignatureFlag(): ?bool | setRequiredSignatureFlag(?bool requiredSignatureFlag): void |
| `outputContent` | [`OutputContent3`](../../doc/models/output-content-3.md) | Required | Content to display or print. This is a sequence of elements if they have different formats. | getOutputContent(): OutputContent3 | setOutputContent(OutputContent3 outputContent): void |

## Example

```php
use AdyenLib\Models\Builders\PrintOutputBuilder;
use AdyenLib\Models\DocumentQualifier2Enum;
use AdyenLib\Models\ResponseMode1Enum;
use AdyenLib\Models\Builders\OutputContent3Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;

$printOutput = PrintOutputBuilder::init(
    DocumentQualifier2Enum::CUSTOMERRECEIPT,
    ResponseMode1Enum::PRINTEND,
    OutputContent3Builder::init(
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

