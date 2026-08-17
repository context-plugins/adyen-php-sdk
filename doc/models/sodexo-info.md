
# Sodexo Info

## Structure

`SodexoInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantContactPhone` | `string` | Required | Sodexo merchantContactPhone | getMerchantContactPhone(): string | setMerchantContactPhone(string merchantContactPhone): void |

## Example

```php
use AdyenLib\Models\Builders\SodexoInfoBuilder;

$sodexoInfo = SodexoInfoBuilder::init(
    'merchantContactPhone4'
)->build();
```

