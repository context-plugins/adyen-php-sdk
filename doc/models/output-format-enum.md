
# Output Format Enum

Format of the content to display or print. Display or print device function.
Possible values:

* **MessageRef**
* **Text**
* **XHTML**
* **BarCode**

## Enumeration

`OutputFormatEnum`

## Fields

| Name |
|  --- |
| `MESSAGEREF` |
| `TEXT` |
| `XHTML` |
| `BARCODE` |

## Example

```php
use AdyenLib\Models\OutputFormatEnum;

$outputFormat = OutputFormatEnum::XHTML;
```

