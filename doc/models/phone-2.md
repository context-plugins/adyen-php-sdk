
# Phone 2

The work phone number provided by the cardholder. The phone number must consist of a country code, followed by the number. If the value you provide does not follow the guidelines, we do not submit it for authentication.

> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`, and did not send the shopper's phone number in `telephoneNumber`.

## Structure

`Phone2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cc` | `?string` | Optional | Country code. Length: 1–3 digits.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `3` | getCc(): ?string | setCc(?string cc): void |
| `subscriber` | `?string` | Optional | Subscriber number. Length: 4-15  digits.<br><br>**Constraints**: *Maximum Length*: `15` | getSubscriber(): ?string | setSubscriber(?string subscriber): void |

## Example

```php
use AdyenLib\Models\Builders\Phone2Builder;

$phone2 = Phone2Builder::init()
    ->cc('cc6')
    ->subscriber('subscriber8')
    ->build();
```

