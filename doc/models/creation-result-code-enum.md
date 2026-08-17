
# Creation Result Code Enum

Notification message. It informs about the outcome of the operation. Possible values:

* CREATED
* ALREADY_EXISTS
* ERROR

## Enumeration

`CreationResultCodeEnum`

## Fields

| Name |
|  --- |
| `ALREADY_EXISTS` |
| `CREATED` |
| `ERROR` |

## Example

```php
use AdyenLib\Models\CreationResultCodeEnum;

$creationResultCode = CreationResultCodeEnum::ALREADY_EXISTS;
```

