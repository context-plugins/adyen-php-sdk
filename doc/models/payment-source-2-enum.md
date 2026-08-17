
# Payment Source 2 Enum

The source used to obtain the payload. Possible values: `qr`, `redirect`, and `pushNotification`.

## Enumeration

`PaymentSource2Enum`

## Fields

| Name |
|  --- |
| `REDIRECT` |
| `QR` |
| `PUSHNOTIFICATION` |

## Example

```php
use AdyenLib\Models\PaymentSource2Enum;

$paymentSource2 = PaymentSource2Enum::PUSHNOTIFICATION;
```

