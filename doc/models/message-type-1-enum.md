
# Message Type 1 Enum

Type of message of the Sale to POI protocol.
Possible values:

* **Notification**
* **Request**
* **Response**

## Enumeration

`MessageType1Enum`

## Fields

| Name |
|  --- |
| `REQUEST` |
| `RESPONSE` |
| `NOTIFICATION` |

## Example

```php
use AdyenLib\Models\MessageType1Enum;

$messageType1 = MessageType1Enum::NOTIFICATION;
```

