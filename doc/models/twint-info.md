
# Twint Info

## Structure

`TwintInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logo` | `string` | Required | Twint logo. Format: Base64-encoded string. | getLogo(): string | setLogo(string logo): void |

## Example

```php
use AdyenLib\Models\Builders\TwintInfoBuilder;

$twintInfo = TwintInfoBuilder::init(
    'logo6'
)->build();
```

