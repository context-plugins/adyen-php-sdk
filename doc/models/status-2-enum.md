
# Status 2 Enum

The status of your request.

If you included `adjustAuthorisationData` in your request, possible values are the following:

* **authorised**

* **refused**

Otherwise, the value is **received**.

## Enumeration

`Status2Enum`

## Fields

| Name |
|  --- |
| `AUTHORISED` |
| `RECEIVED` |
| `REFUSED` |

## Example

```php
use AdyenLib\Models\Status2Enum;

$status2 = Status2Enum::REFUSED;
```

