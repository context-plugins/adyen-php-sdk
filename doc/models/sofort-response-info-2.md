
# Sofort Response Info 2

Sofort details.

## Structure

`SofortResponseInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currencyCode` | `?string` | Optional | Sofort currency code. For example, **EUR**. | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |
| `logo` | `?string` | Optional | Sofort logo. Format: Base64-encoded string. | getLogo(): ?string | setLogo(?string logo): void |

## Example

```php
use AdyenLib\Models\Builders\SofortResponseInfo2Builder;

$sofortResponseInfo2 = SofortResponseInfo2Builder::init()
    ->currencyCode('currencyCode6')
    ->logo('logo8')
    ->build();
```

