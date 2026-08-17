
# Type 212 Enum

The type of error.

Possible values:

* **invalidInput**
* **dataMissing**
* **pendingStatus**
* **dataReview**

## Enumeration

`Type212Enum`

## Fields

| Name |
|  --- |
| `DATAMISSING` |
| `DATAREVIEW` |
| `INVALIDINPUT` |
| `PENDINGSTATUS` |

## Example

```php
use AdyenLib\Models\Type212Enum;

$type212 = Type212Enum::DATAMISSING;
```

