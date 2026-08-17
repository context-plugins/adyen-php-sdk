
# Menu Entry

An entry of the menu to present to the Cashier.
It conveys message text and parameters of the menu entry. This output data could be only provided for an input command, in order to choose an entry of the menu.

## Structure

`MenuEntry`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `menuEntryTag` | [`?string(MenuEntryTag1Enum)`](../../doc/models/menu-entry-tag-1-enum.md) | Optional | Characteristics related to the selection of a menu entry.<br>Possible values:<br><br>* **NonSelectable**<br>* **NonSelectableSubMenu**<br>* **Selectable**<br>* **SubMenu** | getMenuEntryTag(): ?string | setMenuEntryTag(?string menuEntryTag): void |
| `defaultSelectedFlag` | `?bool` | Optional | Selection of a menu entry to be displayed. In Input request message, it allows selection of one or several menu entries before any user action.<br><br>**Default**: `false` | getDefaultSelectedFlag(): ?bool | setDefaultSelectedFlag(?bool defaultSelectedFlag): void |
| `outputFormat` | [`string(OutputFormat2Enum)`](../../doc/models/output-format-2-enum.md) | Required | Possible values:<br><br>* **BarCode**<br>* **MessageRef**<br>* **Text**<br>* **XHTML** | getOutputFormat(): string | setOutputFormat(string outputFormat): void |
| `predefinedContent` | [`?PredefinedContent`](../../doc/models/predefined-content.md) | Optional | Reference of a predefined message to display or print.<br>It conveys information related to the predefined message. | getPredefinedContent(): ?PredefinedContent | setPredefinedContent(?PredefinedContent predefinedContent): void |
| `outputText` | [`?(OutputText[])`](../../doc/models/output-text.md) | Optional | Content of text message to display or print. It conveys Information related to the content of the text message and its format. All the data elements related to the format of the text to display or print are parameters valid for the whole Text content. | getOutputText(): ?array | setOutputText(?array outputText): void |
| `outputXHTML` | `?string` | Optional | XHTML document body containing the message to display or print.<br><br>**Constraints**: *Pattern*: `^.+$` | getOutputXHTML(): ?string | setOutputXHTML(?string outputXHTML): void |

## Example

```php
use AdyenLib\Models\Builders\MenuEntryBuilder;
use AdyenLib\Models\OutputFormat2Enum;
use AdyenLib\Models\MenuEntryTag1Enum;
use AdyenLib\Models\Builders\PredefinedContentBuilder;
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;

$menuEntry = MenuEntryBuilder::init(
    OutputFormat2Enum::MESSAGEREF
)
    ->menuEntryTag(MenuEntryTag1Enum::SELECTABLE)
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
                ->build()
        ]
    )
    ->outputXHTML('OutputXHTML8')
    ->build();
```

