
# Status 15 Enum

The status of the transfer.

Possible values:

- **credited**: the funds are credited to your user's transfer instrument or bank account.- **accepted**: the request is accepted by the integration.

## Enumeration

`Status15Enum`

## Fields

| Name |
|  --- |
| `CREDITED` |
| `ACCEPTED` |

## Example

```php
use AdyenLib\Models\Status15Enum;

$status15 = Status15Enum::CREDITED;
```

