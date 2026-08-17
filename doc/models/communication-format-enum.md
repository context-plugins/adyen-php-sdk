
# Communication Format Enum

Format or protocol for receiving webhooks. Possible values:

* **soap**
* **http**
* **json**

## Enumeration

`CommunicationFormatEnum`

## Fields

| Name |
|  --- |
| `HTTP` |
| `JSON` |
| `SOAP` |

## Example

```php
use AdyenLib\Models\CommunicationFormatEnum;

$communicationFormat = CommunicationFormatEnum::HTTP;
```

