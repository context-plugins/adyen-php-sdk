
# Twint Info 2

Details to provide if `type` is **twint**.

## Structure

`TwintInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logo` | `string` | Required | Twint logo. Format: Base64-encoded string. | getLogo(): string | setLogo(string logo): void |

## Example

```php
use AdyenLib\Models\Builders\TwintInfo2Builder;

$twintInfo2 = TwintInfo2Builder::init(
    'logo6'
)->build();
```

