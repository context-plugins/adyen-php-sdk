
# Type 15 Enum

The type of the document. Possible values: **ID**, **DRIVINGLICENSE**, **PASSPORT**, **SOCIALSECURITY**, **VISA**.

To delete an existing entry for a document `type`, send only the `type` field in your request.

## Enumeration

`Type15Enum`

## Fields

| Name |
|  --- |
| `DRIVINGLICENSE` |
| `ID` |
| `PASSPORT` |
| `SOCIALSECURITY` |
| `VISA` |

## Example

```php
use AdyenLib\Models\Type15Enum;

$type15 = Type15Enum::ID;
```

