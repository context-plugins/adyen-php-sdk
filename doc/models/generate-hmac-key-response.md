
# Generate Hmac Key Response

## Structure

`GenerateHmacKeyResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hmacKey` | `string` | Required | The HMAC key generated for this webhook. | getHmacKey(): string | setHmacKey(string hmacKey): void |

## Example

```php
use AdyenLib\Models\Builders\GenerateHmacKeyResponseBuilder;

$generateHmacKeyResponse = GenerateHmacKeyResponseBuilder::init(
    'hmacKey6'
)->build();
```

