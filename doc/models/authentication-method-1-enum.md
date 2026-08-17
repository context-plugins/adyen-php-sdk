
# Authentication Method 1 Enum

## Enumeration

`AuthenticationMethod1Enum`

## Fields

| Name |
|  --- |
| `BYPASS` |
| `MANUALVERIFICATION` |
| `MERCHANTAUTHENTICATION` |
| `OFFLINEPIN` |
| `ONLINEPIN` |
| `PAPERSIGNATURE` |
| `SECUREDCHANNEL` |
| `SECURECERTIFICATE` |
| `SECURENOCERTIFICATE` |
| `SIGNATURECAPTURE` |
| `UNKNOWNMETHOD` |

## Example

```php
use AdyenLib\Models\AuthenticationMethod1Enum;

$authenticationMethod1 = AuthenticationMethod1Enum::PAPERSIGNATURE;
```

