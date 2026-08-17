
# Generate Client Key Response

## Structure

`GenerateClientKeyResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientKey` | `string` | Required | Generated client key | getClientKey(): string | setClientKey(string clientKey): void |

## Example

```php
use AdyenLib\Models\Builders\GenerateClientKeyResponseBuilder;

$generateClientKeyResponse = GenerateClientKeyResponseBuilder::init(
    'clientKey8'
)->build();
```

