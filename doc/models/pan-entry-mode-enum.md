
# Pan Entry Mode Enum

Indicates the method used for entering the PAN to initiate a transaction.

Possible values: **manual**, **chip**, **magstripe**, **contactless**, **cof**, **ecommerce**, **token**.

## Enumeration

`PanEntryModeEnum`

## Fields

| Name |
|  --- |
| `CHIP` |
| `COF` |
| `CONTACTLESS` |
| `ECOMMERCE` |
| `MAGSTRIPE` |
| `MANUAL` |
| `TOKEN` |

## Example

```php
use AdyenLib\Models\PanEntryModeEnum;

$panEntryMode = PanEntryModeEnum::TOKEN;
```

