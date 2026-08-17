
# Sofort Info

## Structure

`SofortInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currencyCode` | `string` | Required | Sofort currency code. For example, **EUR**. | getCurrencyCode(): string | setCurrencyCode(string currencyCode): void |
| `logo` | `string` | Required | Sofort logo. Format: Base64-encoded string. | getLogo(): string | setLogo(string logo): void |

## Example

```php
use AdyenLib\Models\Builders\SofortInfoBuilder;

$sofortInfo = SofortInfoBuilder::init(
    'currencyCode6',
    'logo2'
)->build();
```

