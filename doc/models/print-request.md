
# Print Request

Content of the Print Request message.
It conveys the complete data to print and how to process the print.

## Structure

`PrintRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `printOutput` | [`PrintOutput2`](../../doc/models/print-output-2.md) | Required | Information to print and how to process it. | getPrintOutput(): PrintOutput2 | setPrintOutput(PrintOutput2 printOutput): void |

## Example

```php
use AdyenLib\Models\Builders\PrintRequestBuilder;
use AdyenLib\Models\Builders\PrintOutput2Builder;
use AdyenLib\Models\DocumentQualifier2Enum;
use AdyenLib\Models\ResponseMode1Enum;
use AdyenLib\Models\Builders\OutputContent3Builder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;

$printRequest = PrintRequestBuilder::init(
    PrintOutput2Builder::init(
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
        ->build()
)->build();
```

