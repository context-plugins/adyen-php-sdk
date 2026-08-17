
# Twint Response Info

## Structure

`TwintResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logo` | `?string` | Optional | Twint logo. Format: Base64-encoded string. | getLogo(): ?string | setLogo(?string logo): void |

## Example

```php
use AdyenLib\Models\Builders\TwintResponseInfoBuilder;

$twintResponseInfo = TwintResponseInfoBuilder::init()
    ->logo('logo0')
    ->build();
```

