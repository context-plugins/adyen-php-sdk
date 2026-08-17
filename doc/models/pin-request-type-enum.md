
# PIN Request Type Enum

Type of PIN Service.
Possible values:

* **PINVerify**
* **PINVerifyOnly**
* **PINEnter**

## Enumeration

`PINRequestTypeEnum`

## Fields

| Name |
|  --- |
| `PINVERIFY` |
| `PINVERIFYONLY` |
| `PINENTER` |

## Example

```php
use AdyenLib\Models\PINRequestTypeEnum;

$pINRequestType = PINRequestTypeEnum::PINENTER;
```

