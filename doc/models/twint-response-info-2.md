
# Twint Response Info 2

**twint** details

## Structure

`TwintResponseInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logo` | `?string` | Optional | Twint logo. Format: Base64-encoded string. | getLogo(): ?string | setLogo(?string logo): void |

## Example

```php
use AdyenLib\Models\Builders\TwintResponseInfo2Builder;

$twintResponseInfo2 = TwintResponseInfo2Builder::init()
    ->logo('logo2')
    ->build();
```

