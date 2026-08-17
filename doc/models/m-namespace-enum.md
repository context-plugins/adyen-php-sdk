
# M Namespace Enum

The namespace that corresponds to the reason code.

Possible values:

* **ukFpsRejectionCode**
* **ukFpsReturnReasonCode**
* **usAchReturnReasonCode**
* **iso8583ResponseCode**

## Enumeration

`MNamespaceEnum`

## Fields

| Name |
|  --- |
| `ISO8583RESPONSECODE` |
| `UKFPSREJECTIONCODE` |
| `UKFPSRETURNREASONCODE` |
| `USACHRETURNREASONCODE` |

## Example

```php
use AdyenLib\Models\NamespaceEnum;

$namespace = NamespaceEnum::ISO8583RESPONSECODE;
```

