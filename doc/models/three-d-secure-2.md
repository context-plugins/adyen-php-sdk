
# Three D Secure 2

The data of the result from the 3DS authentication.

## Structure

`ThreeDSecure2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acsTransactionId` | `?string` | Optional | The transaction identifier for the Access Control Server | getAcsTransactionId(): ?string | setAcsTransactionId(?string acsTransactionId): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDSecure2Builder;

$threeDSecure2 = ThreeDSecure2Builder::init()
    ->acsTransactionId('acsTransactionId6')
    ->build();
```

