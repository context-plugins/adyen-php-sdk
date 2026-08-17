
# Type 512 Enum

The type of error.

Possible values:

* **invalidInput**
* **dataMissing**
* **pendingStatus**
* **rejected**
* **dataReview**

## Enumeration

`Type512Enum`

## Fields

| Name |
|  --- |
| `DATAMISSING` |
| `DATAREVIEW` |
| `INVALIDINPUT` |
| `PENDINGSTATUS` |
| `REJECTED` |

## Example

```php
use AdyenLib\Models\Type512Enum;

$type512 = Type512Enum::REJECTED;
```

