
# Input Command 1 Enum

Type of requested input. Can be: **GetConfirmation**, **TextString**, **DigitString**, **DecimalString** or **GetMenuEntry**.
Possible values:

* **DecimalString**
* **DigitString**
* **GetAnyKey**
* **GetConfirmation**
* **GetFunctionKey**
* **GetMenuEntry**
* **Password**
* **SiteManager**
* **TextString**

## Enumeration

`InputCommand1Enum`

## Fields

| Name |
|  --- |
| `GETANYKEY` |
| `GETCONFIRMATION` |
| `SITEMANAGER` |
| `TEXTSTRING` |
| `DIGITSTRING` |
| `DECIMALSTRING` |
| `GETFUNCTIONKEY` |
| `GETMENUENTRY` |
| `PASSWORD` |

## Example

```php
use AdyenLib\Models\InputCommand1Enum;

$inputCommand1 = InputCommand1Enum::GETMENUENTRY;
```

