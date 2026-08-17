
# Abort Request

Body of the Abort Request message.
It conveys Information requested for identification of the message request carrying the transaction to abort. A message to display on the CustomerError Device could be sent by the Sale System (DisplayOutput).

## Structure

`AbortRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageReference` | [`MessageReference4`](../../doc/models/message-reference-4.md) | Required | Identification of a previous POI transaction. | getMessageReference(): MessageReference4 | setMessageReference(MessageReference4 messageReference): void |
| `abortReason` | `string` | Required | Reason of aborting a transaction.<br><br>**Constraints**: *Pattern*: `^.+$` | getAbortReason(): string | setAbortReason(string abortReason): void |
| `displayOutput` | [`?DisplayOutput1`](../../doc/models/display-output-1.md) | Optional | Information to display and the way to process the display.<br>To display an abort message to the Customer. | getDisplayOutput(): ?DisplayOutput1 | setDisplayOutput(?DisplayOutput1 displayOutput): void |

## Example

```php
use AdyenLib\Models\Builders\AbortRequestBuilder;
use AdyenLib\Models\Builders\MessageReference4Builder;
use AdyenLib\Models\MessageCategory2Enum;
use AdyenLib\Models\Builders\DisplayOutput1Builder;
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

$abortRequest = AbortRequestBuilder::init(
    MessageReference4Builder::init()
        ->messageCategory(MessageCategory2Enum::PAYMENT)
        ->serviceID('ServiceID0')
        ->deviceID('DeviceID2')
        ->saleID('SaleID8')
        ->pOIID('POIID2')
        ->build(),
    'AbortReason0'
)
    ->displayOutput(
        DisplayOutput1Builder::init(
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

