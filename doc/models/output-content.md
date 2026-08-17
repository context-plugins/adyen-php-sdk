
# Output Content

Content to display or print.
This is a sequence of elements if they have different formats.

## Structure

`OutputContent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `outputFormat` | [`string(OutputFormat1Enum)`](../../doc/models/output-format-1-enum.md) | Required | Format of the content to display or print.<br>Possible values:<br><br>* **BarCode**<br>* **MessageRef**<br>* **Text**<br>* **XHTML** | getOutputFormat(): string | setOutputFormat(string outputFormat): void |
| `predefinedContent` | [`?PredefinedContent1`](../../doc/models/predefined-content-1.md) | Optional | Reference of a predefined message to display or print.<br>Mandatory, if `OutputFormat` is MessageRef, not allowed otherwise. | getPredefinedContent(): ?PredefinedContent1 | setPredefinedContent(?PredefinedContent1 predefinedContent): void |
| `outputText` | [`?(OutputText[])`](../../doc/models/output-text.md) | Optional | Content of text message to display or print.<br>Mandatory, if `OutputFormat` is Text, not allowed otherwise. One instance of `OutputText` per shared format. | getOutputText(): ?array | setOutputText(?array outputText): void |
| `outputXHTML` | `?string` | Optional | XHTML document body containing the message to display or print.<br>Mandatory if `OutputFormat` is XHTML, not allowed otherwise.<br><br>**Constraints**: *Pattern*: `^.{0,262144}$` | getOutputXHTML(): ?string | setOutputXHTML(?string outputXHTML): void |
| `outputBarcode` | [`?OutputBarcode1`](../../doc/models/output-barcode-1.md) | Optional | Barcode content to display or print.<br>Mandatory if `OutputFormat` is Barcode, not allowed otherwise. | getOutputBarcode(): ?OutputBarcode1 | setOutputBarcode(?OutputBarcode1 outputBarcode): void |

## Example

```php
use AdyenLib\Models\Builders\OutputContentBuilder;
use AdyenLib\Models\OutputFormat1Enum;
use AdyenLib\Models\Builders\PredefinedContent1Builder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;
use AdyenLib\Models\Builders\OutputBarcode1Builder;

$outputContent = OutputContentBuilder::init(
    OutputFormat1Enum::MESSAGEREF
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
                ->build(),
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
    ->outputXHTML('OutputXHTML0')
    ->outputBarcode(
        OutputBarcode1Builder::init(
            'BarcodeValue2'
        )->build()
    )->build();
```

