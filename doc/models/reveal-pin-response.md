
# Reveal Pin Response

## Structure

`RevealPinResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `encryptedPinBlock` | `string` | Required | The encrypted [PIN block](https://www.pcisecuritystandards.org/glossary/pin-block). | getEncryptedPinBlock(): string | setEncryptedPinBlock(string encryptedPinBlock): void |
| `token` | `string` | Required | The 16-digit token that you need to extract the `encryptedPinBlock`. | getToken(): string | setToken(string token): void |

## Example

```php
use AdyenLib\Models\Builders\RevealPinResponseBuilder;

$revealPinResponse = RevealPinResponseBuilder::init(
    'encryptedPinBlock0',
    'token0'
)->build();
```

