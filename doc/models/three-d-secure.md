
# Three D Secure

## Structure

`ThreeDSecure`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acsTransactionId` | `?string` | Optional | The transaction identifier for the Access Control Server | getAcsTransactionId(): ?string | setAcsTransactionId(?string acsTransactionId): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDSecureBuilder;

$threeDSecure = ThreeDSecureBuilder::init()
    ->acsTransactionId('acsTransactionId8')
    ->build();
```

