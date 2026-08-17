
# Channel 3 Enum

The platform where a payment transaction takes place. This field can be used for filtering out payment methods that are only available on specific platforms. Possible values:

* iOS
* Android
* Web

## Enumeration

`Channel3Enum`

## Fields

| Name |
|  --- |
| `IOS` |
| `ANDROID` |
| `WEB` |

## Example

```php
use AdyenLib\Models\Channel3Enum;

$channel3 = Channel3Enum::WEB;
```

