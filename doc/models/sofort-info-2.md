
# Sofort Info 2

Sofort details.

## Structure

`SofortInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currencyCode` | `string` | Required | Sofort currency code. For example, **EUR**. | getCurrencyCode(): string | setCurrencyCode(string currencyCode): void |
| `logo` | `string` | Required | Sofort logo. Format: Base64-encoded string. | getLogo(): string | setLogo(string logo): void |

## Example

```php
use AdyenLib\Models\Builders\SofortInfo2Builder;

$sofortInfo2 = SofortInfo2Builder::init(
    'currencyCode0',
    'logo6'
)->build();
```

