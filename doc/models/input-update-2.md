
# Input Update 2

Content of the Input Update message.

## Structure

`InputUpdate2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageReference` | [`MessageReference`](../../doc/models/message-reference.md) | Required | Identification of a previous POI transaction.<br>To abort a transaction in progress or to request the status of a transaction from which no response has been received. It identifies the message header of the message request to abort or request the status. | getMessageReference(): MessageReference | setMessageReference(MessageReference messageReference): void |
| `outputContent` | [`OutputContent`](../../doc/models/output-content.md) | Required | Content to display or print.<br>This is a sequence of elements if they have different formats. | getOutputContent(): OutputContent | setOutputContent(OutputContent outputContent): void |
| `menuEntry` | [`?(MenuEntry[])`](../../doc/models/menu-entry.md) | Optional | - | getMenuEntry(): ?array | setMenuEntry(?array menuEntry): void |
| `outputSignature` | `?string` | Optional | **Constraints**: *Pattern*: `^.+$` | getOutputSignature(): ?string | setOutputSignature(?string outputSignature): void |
| `minLength` | `?int` | Optional | - | getMinLength(): ?int | setMinLength(?int minLength): void |
| `maxLength` | `?int` | Optional | - | getMaxLength(): ?int | setMaxLength(?int maxLength): void |
| `maxDecimalLength` | `?int` | Optional | - | getMaxDecimalLength(): ?int | setMaxDecimalLength(?int maxDecimalLength): void |

## Example

```php
use AdyenLib\Models\Builders\InputUpdate2Builder;
use AdyenLib\Models\Builders\MessageReferenceBuilder;
use AdyenLib\Models\MessageCategory2Enum;
use AdyenLib\Models\Builders\OutputContentBuilder;
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

$inputUpdate2 = InputUpdate2Builder::init(
    MessageReferenceBuilder::init()
        ->messageCategory(MessageCategory2Enum::PAYMENT)
        ->serviceID('ServiceID0')
        ->deviceID('DeviceID2')
        ->saleID('SaleID8')
        ->pOIID('POIID2')
        ->build(),
    OutputContentBuilder::init(
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
    ->minLength(238)
    ->maxLength(6)
    ->maxDecimalLength(14)
    ->build();
```

