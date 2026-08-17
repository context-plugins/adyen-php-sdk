
# Response Mode 1 Enum

Message response awaited by the initiator of the Request. Allows various types and synchronisation of requests for Print or Sound.
Possible values:

* **Immediate**
* **NotRequired**
* **PrintEnd**
* **SoundEnd**

## Enumeration

`ResponseMode1Enum`

## Fields

| Name |
|  --- |
| `NOTREQUIRED` |
| `IMMEDIATE` |
| `PRINTEND` |
| `SOUNDEND` |

## Example

```php
use AdyenLib\Models\ResponseMode1Enum;

$responseMode1 = ResponseMode1Enum::NOTREQUIRED;
```

