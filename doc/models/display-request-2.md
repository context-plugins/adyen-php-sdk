
# Display Request 2

Content of the Display Request message.

## Structure

`DisplayRequest2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `displayOutput` | [`DisplayOutput[]`](../../doc/models/display-output.md) | Required | Information to display and the way to process the display.<br>Complete display content for output devices. At most one DisplayOutput per Device/ InfoQualify pair. | getDisplayOutput(): array | setDisplayOutput(array displayOutput): void |

## Example

```php
use AdyenLib\Models\Builders\DisplayRequest2Builder;
use AdyenLib\Models\Builders\DisplayOutputBuilder;
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

$displayRequest2 = DisplayRequest2Builder::init(
    [
        DisplayOutputBuilder::init(
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
            ->responseRequiredFlag(true)
            ->minimumDisplayTime(0)
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
    ]
)->build();
```

