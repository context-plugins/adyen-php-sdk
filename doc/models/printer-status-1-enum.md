
# Printer Status 1 Enum

Possible values:

* **NoPaper**
* **OK**
* **OutOfOrder**
* **PaperJam**
* **PaperLow**

## Enumeration

`PrinterStatus1Enum`

## Fields

| Name |
|  --- |
| `OK` |
| `PAPERLOW` |
| `NOPAPER` |
| `PAPERJAM` |
| `OUTOFORDER` |

## Example

```php
use AdyenLib\Models\PrinterStatus1Enum;

$printerStatus1 = PrinterStatus1Enum::OUTOFORDER;
```

