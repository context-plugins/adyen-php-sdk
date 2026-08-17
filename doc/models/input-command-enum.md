
# Input Command Enum

Possible values:

* **GetAnyKey**
* **GetConfirmation**
* **SiteManager**
* **TextString**
* **DigitString**
* **DecimalString**
* **GetFunctionKey**
* **GetMenuEntry**
* **Password**

## Enumeration

`InputCommandEnum`

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
use AdyenLib\Models\InputCommandEnum;

$inputCommand = InputCommandEnum::DECIMALSTRING;
```

