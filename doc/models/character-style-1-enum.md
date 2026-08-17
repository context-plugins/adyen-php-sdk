
# Character Style 1 Enum

Typographic style of the sequence of characters to display or print. Absence of this data element means the characters have normal style.
Possible values:

* **Bold**
* **Italic**
* **Normal**
* **Underline**

## Enumeration

`CharacterStyle1Enum`

## Fields

| Name |
|  --- |
| `NORMAL` |
| `BOLD` |
| `ITALIC` |
| `UNDERLINE` |

## Example

```php
use AdyenLib\Models\CharacterStyle1Enum;

$characterStyle1 = CharacterStyle1Enum::ITALIC;
```

