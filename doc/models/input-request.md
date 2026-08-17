
# Input Request

Content of the `InputRequest` message. It conveys the data to display and how to process it. In addition to the display on the Input Device, it might contain an operation (the `DisplayOutput` element) per Display Device type.

## Structure

`InputRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `displayOutput` | [`?DisplayOutput2`](../../doc/models/display-output-2.md) | Optional | Information to display and the way to process the display. | getDisplayOutput(): ?DisplayOutput2 | setDisplayOutput(?DisplayOutput2 displayOutput): void |
| `inputData` | [`InputData2`](../../doc/models/input-data-2.md) | Required | Information related to an Input request. It conveys the target input logical device, the type of input command, and possible minimum and maximum length of the input. In addition, if the requestor might require to receive an Event Notification if a card is inserted in a card reader, with the `NotifyCardInputFlag`. | getInputData(): InputData2 | setInputData(InputData2 inputData): void |

## Example

```php
use AdyenLib\Models\Builders\InputRequestBuilder;
use AdyenLib\Models\Builders\InputData2Builder;
use AdyenLib\Models\Device2Enum;
use AdyenLib\Models\InfoQualify2Enum;
use AdyenLib\Models\InputCommand1Enum;
use AdyenLib\Models\Builders\DisplayOutput2Builder;
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

$inputRequest = InputRequestBuilder::init(
    InputData2Builder::init(
        Device2Enum::CASHIERDISPLAY,
        InfoQualify2Enum::CUSTOMERASSISTANCE,
        InputCommand1Enum::GETANYKEY
    )
        ->notifyCardInputFlag(false)
        ->maxInputTime(154)
        ->immediateResponseFlag(false)
        ->minLength(242)
        ->maxLength(246)
        ->waitUserValidationFlag(true)
        ->fromRightToLeftFlag(false)
        ->maskCharactersFlag(false)
        ->beepKeyFlag(false)
        ->globalCorrectionFlag(false)
        ->disableCancelFlag(false)
        ->disableCorrectFlag(false)
        ->disableValidFlag(false)
        ->menuBackFlag(false)
        ->build()
)
    ->displayOutput(
        DisplayOutput2Builder::init(
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
    ->build();
```

