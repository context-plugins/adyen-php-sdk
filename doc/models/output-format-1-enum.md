
# Output Format 1 Enum

Format of the content to display or print.
Possible values:

* **BarCode**
* **MessageRef**
* **Text**
* **XHTML**

## Enumeration

`OutputFormat1Enum`

## Fields

| Name |
|  --- |
| `MESSAGEREF` |
| `TEXT` |
| `XHTML` |
| `BARCODE` |

## Example

```php
use AdyenLib\Models\OutputFormat1Enum;

$outputFormat1 = OutputFormat1Enum::XHTML;
```

