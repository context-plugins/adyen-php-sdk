
# File 2

For `eap` **tls**. The certificate chain for the terminals. All terminals in the same network will use the same EAP client certificate.

## Structure

`File2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | `string` | Required | The certificate content converted to a Base64-encoded string. | getData(): string | setData(string data): void |
| `name` | `string` | Required | The name of the certificate. Must be unique across Wi-Fi profiles. | getName(): string | setName(string name): void |

## Example

```php
use AdyenLib\Models\Builders\File2Builder;

$file2 = File2Builder::init(
    'data2',
    'name2'
)->build();
```

