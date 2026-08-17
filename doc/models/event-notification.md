
# Event Notification

Content of the EventNotification message.
It conveys Information related to the event, and possible action (maintenance, message to display).

## Structure

`EventNotification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `timeStamp` | `DateTime` | Required | Date and time of a transaction for the Sale System, the POI System or the Acquirer. | getTimeStamp(): \DateTime | setTimeStamp(\DateTime timeStamp): void |
| `eventToNotify` | [`string(EventToNotify1Enum)`](../../doc/models/event-to-notify-1-enum.md) | Required | Event the POI notifies to the Sale System.<br>Possible values:<br><br>* **Abort**<br>* **BeginMaintenance**<br>* **CardInserted**<br>* **CardRemoved**<br>* **Completed**<br>* **CustomerLanguage**<br>* **EndMaintenance**<br>* **Initialised**<br>* **KeyPressed**<br>* **OutOfOrder**<br>* **Reject**<br>* **SaleAdmin**<br>* **SaleWakeUp**<br>* **ScanBarcodeResult**<br>* **SecurityAlarm**<br>* **Shutdown**<br>* **StopAssistance**<br>* **UseAnotherCardForPreauth** | getEventToNotify(): string | setEventToNotify(string eventToNotify): void |
| `eventDetails` | `?string` | Optional | Information about the event the POI notifies to the Sale System.<br>If present, the Sale logs it for further examination.<br><br>**Constraints**: *Pattern*: `^.+$` | getEventDetails(): ?string | setEventDetails(?string eventDetails): void |
| `rejectedMessage` | `?string` | Optional | Message request rejected by the receiver.<br>Mandatory if EventToNotify is Reject, absent in other cases.<br><br>**Constraints**: *Pattern*: `^.+$` | getRejectedMessage(): ?string | setRejectedMessage(?string rejectedMessage): void |
| `maintenanceRequiredFlag` | `?bool` | Optional | Indicates if the occurred event requires maintenance call or action.<br><br>**Default**: `false` | getMaintenanceRequiredFlag(): ?bool | setMaintenanceRequiredFlag(?bool maintenanceRequiredFlag): void |
| `displayOutput` | [`?(DisplayOutput[])`](../../doc/models/display-output.md) | Optional | Information to display and the way to process the display.<br>To display an event message. | getDisplayOutput(): ?array | setDisplayOutput(?array displayOutput): void |

## Example

```php
use AdyenLib\Models\Builders\EventNotificationBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\EventToNotify1Enum;
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

$eventNotification = EventNotificationBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    EventToNotify1Enum::CARDREMOVED
)
    ->eventDetails('EventDetails2')
    ->rejectedMessage('RejectedMessage2')
    ->maintenanceRequiredFlag(false)
    ->displayOutput(
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
                ->build(),
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
                ->build(),
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
        ]
    )
    ->build();
```

