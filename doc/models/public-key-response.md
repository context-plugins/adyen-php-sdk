
# Public Key Response

## Structure

`PublicKeyResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `publicKey` | `string` | Required | The public key you need for encrypting a symmetric session key. | getPublicKey(): string | setPublicKey(string publicKey): void |
| `publicKeyExpiryDate` | `string` | Required | The expiry date of the public key. | getPublicKeyExpiryDate(): string | setPublicKeyExpiryDate(string publicKeyExpiryDate): void |

## Example

```php
use AdyenLib\Models\Builders\PublicKeyResponseBuilder;

$publicKeyResponse = PublicKeyResponseBuilder::init(
    'publicKey4',
    'publicKeyExpiryDate2'
)->build();
```

