
# Output Text

Content of text message to display or print.
It conveys information related to the content of the text message and its format. All the data elements related to the format of the text to display or print are parameters valid for the whole text content.

## Structure

`OutputText`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `text` | `string` | Required | Content of text message to display, print or play. | getText(): string | setText(string text): void |
| `characterSet` | `?int` | Optional | Character height of the text string to display or print. Absence of this data element means the characters have normal height. | getCharacterSet(): ?int | setCharacterSet(?int characterSet): void |
| `startRow` | `?int` | Optional | Row where the text string has to be displayed or printed.<br><br>**Constraints**: `>= 1`, `<= 500` | getStartRow(): ?int | setStartRow(?int startRow): void |
| `startColumn` | `?int` | Optional | Column where the text string has to be displayed or printed.<br><br>**Constraints**: `>= 1`, `<= 500` | getStartColumn(): ?int | setStartColumn(?int startColumn): void |
| `characterWidth` | [`?string(CharacterWidth1Enum)`](../../doc/models/character-width-1-enum.md) | Optional | Character width of the text string to display or print. Absence of this data element means the characters have normal width.<br>Possible values:<br><br>* **DoubleWidth**<br>* **SingleWidth** | getCharacterWidth(): ?string | setCharacterWidth(?string characterWidth): void |
| `characterHeight` | [`?string(CharacterHeight1Enum)`](../../doc/models/character-height-1-enum.md) | Optional | Character height of the text string to display or print. Absence of this data element means the characters have normal height.<br>Possible values:<br><br>* **DoubleHeight**<br>* **HalfHeight**<br>* **SingleHeight** | getCharacterHeight(): ?string | setCharacterHeight(?string characterHeight): void |
| `characterStyle` | [`?string(CharacterStyle1Enum)`](../../doc/models/character-style-1-enum.md) | Optional | Typographic style of the sequence of characters to display or print. Absence of this data element means the characters have normal style.<br>Possible values:<br><br>* **Bold**<br>* **Italic**<br>* **Normal**<br>* **Underline** | getCharacterStyle(): ?string | setCharacterStyle(?string characterStyle): void |
| `alignment` | [`?string(Alignment1Enum)`](../../doc/models/alignment-1-enum.md) | Optional | Alignment of the text string on the display line or print line. Absence of this data element means the characters have normal alignment.<br>Possible values:<br><br>* **Centred**<br>* **Justified**<br>* **Left**<br>* **Right** | getAlignment(): ?string | setAlignment(?string alignment): void |
| `endOfLineFlag` | `?bool` | Optional | Indicates if the text is at the end of a line. Allows the display or the print of a new line and a carry-over return characters after the formatted text.<br><br>**Default**: `true` | getEndOfLineFlag(): ?bool | setEndOfLineFlag(?bool endOfLineFlag): void |

## Example

```php
use AdyenLib\Models\Builders\OutputTextBuilder;
use AdyenLib\Models\CharacterWidth1Enum;
use AdyenLib\Models\CharacterHeight1Enum;

$outputText = OutputTextBuilder::init(
    'Text4'
)
    ->characterSet(178)
    ->startRow(90)
    ->startColumn(204)
    ->characterWidth(CharacterWidth1Enum::SINGLEWIDTH)
    ->characterHeight(CharacterHeight1Enum::SINGLEHEIGHT)
    ->endOfLineFlag(true)
    ->build();
```

