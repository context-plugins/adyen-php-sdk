
# Printer Status Enum

Indicates if the printer is working and usable.
Possible values:

* **OK**
* **PaperLow**
* **NoPaper**
* **PaperJam**
* **OutOfOrder**

## Enumeration

`PrinterStatusEnum`

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
use AdyenLib\Models\PrinterStatusEnum;

$printerStatus = PrinterStatusEnum::PAPERLOW;
```

