
# Security Trailer

It contains information related to the security of the message.
SecurityTrailer as used by Adyen.

## Structure

`SecurityTrailer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adyenCryptoVersion` | `int` | Required | - | getAdyenCryptoVersion(): int | setAdyenCryptoVersion(int adyenCryptoVersion): void |
| `keyIdentifier` | `string` | Required | **Constraints**: *Pattern*: `^.+$` | getKeyIdentifier(): string | setKeyIdentifier(string keyIdentifier): void |
| `keyVersion` | `int` | Required | - | getKeyVersion(): int | setKeyVersion(int keyVersion): void |
| `nonce` | `string` | Required | **Constraints**: *Pattern*: `^.+$` | getNonce(): string | setNonce(string nonce): void |
| `hmac` | `string` | Required | **Constraints**: *Pattern*: `^.+$` | getHmac(): string | setHmac(string hmac): void |

## Example

```php
use AdyenLib\Models\Builders\SecurityTrailerBuilder;

$securityTrailer = SecurityTrailerBuilder::init(
    88,
    'KeyIdentifier8',
    22,
    'Nonce0',
    'Hmac2'
)->build();
```

