
# Display Output

Information to display and how to process it.
Contains a complete display operation for a Display or an Input Device type. For the Input Devices, Diagnosis and `EnableService`, `ResponseRequiredFlag`, and `MinimumDisplayTime` shall be absent.

## Structure

`DisplayOutput`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `responseRequiredFlag` | `?bool` | Optional | Indicates if the message response is required.<br><br>**Default**: `true` | getResponseRequiredFlag(): ?bool | setResponseRequiredFlag(?bool responseRequiredFlag): void |
| `minimumDisplayTime` | `?int` | Optional | Number of seconds the message has to be displayed.<br><br>**Default**: `0`<br><br>**Constraints**: `>= 0`, `<= 999` | getMinimumDisplayTime(): ?int | setMinimumDisplayTime(?int minimumDisplayTime): void |
| `device` | [`string(Device11Enum)`](../../doc/models/device-11-enum.md) | Required | Logical device located on a Sale Terminal or a POI Terminal, in terms of class of information to output (display, print, or store), or input (keyboard) for the Cashier or the Customer.<br>Possible values:<br><br>* **CashierDisplay**<br>* **CashierInput**<br>* **CustomerDisplay**<br>* **CustomerInput** | getDevice(): string | setDevice(string device): void |
| `infoQualify` | [`string(InfoQualify1Enum)`](../../doc/models/info-qualify-1-enum.md) | Required | Qualification of the information to sent to an output logical device, to display or print to the Cashier or the Customer. Allows the manager of the device, Sale or POI Terminal, to send the information to a particular physical device or to present the information accordingly.<br>Possible values:<br><br>* **CustomerAssistance**<br>* **Display**<br>* **Document**<br>* **Error**<br>* **Input**<br>* **POIReplication**<br>* **Receipt**<br>* **Sound**<br>* **Status**<br>* **Voucher** | getInfoQualify(): string | setInfoQualify(string infoQualify): void |
| `outputContent` | [`OutputContent1`](../../doc/models/output-content-1.md) | Required | Content to display or print. | getOutputContent(): OutputContent1 | setOutputContent(OutputContent1 outputContent): void |
| `menuEntry` | [`?(MenuEntry[])`](../../doc/models/menu-entry.md) | Optional | An entry of the menu to present to the Cashier. It conveys the message text and parameters of the menu entry. This output data could be only provided for an input command, in order to choose an entryof the menu. | getMenuEntry(): ?array | setMenuEntry(?array menuEntry): void |
| `outputSignature` | `?string` | Optional | Vendor-specific signature of the text message to display or print.<br>If protection has to be provided to the vendor on the text to display or print.<br><br>**Constraints**: *Pattern*: `^.+$` | getOutputSignature(): ?string | setOutputSignature(?string outputSignature): void |

## Example

```php
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

$displayOutput = DisplayOutputBuilder::init(
    Device11Enum::CASHIERINPUT,
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
                ->build()
        ]
    )
    ->outputSignature('OutputSignature4')
    ->build();
```

