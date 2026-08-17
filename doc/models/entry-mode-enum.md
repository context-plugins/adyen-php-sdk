
# Entry Mode Enum

## Enumeration

`EntryModeEnum`

## Fields

| Name |
|  --- |
| `RFID` |
| `KEYED` |
| `MANUAL` |
| `FILE` |
| `SCANNED` |
| `MAGSTRIPE` |
| `ICC` |
| `SYNCHRONOUSICC` |
| `TAPPED` |
| `CONTACTLESS` |
| `MOBILE` |

## Example

```php
use AdyenLib\Models\EntryModeEnum;

$entryMode = EntryModeEnum::SYNCHRONOUSICC;
```

