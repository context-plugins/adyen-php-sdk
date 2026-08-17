
# Sofort Response Info

## Structure

`SofortResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currencyCode` | `?string` | Optional | Sofort currency code. For example, **EUR**. | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |
| `logo` | `?string` | Optional | Sofort logo. Format: Base64-encoded string. | getLogo(): ?string | setLogo(?string logo): void |

## Example

```php
use AdyenLib\Models\Builders\SofortResponseInfoBuilder;

$sofortResponseInfo = SofortResponseInfoBuilder::init()
    ->currencyCode('currencyCode0')
    ->logo('logo4')
    ->build();
```

