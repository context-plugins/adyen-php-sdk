
# Sodexo Info 2

Details to provide if `type` is **sodexo**.

## Structure

`SodexoInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantContactPhone` | `string` | Required | Sodexo merchantContactPhone | getMerchantContactPhone(): string | setMerchantContactPhone(string merchantContactPhone): void |

## Example

```php
use AdyenLib\Models\Builders\SodexoInfo2Builder;

$sodexoInfo2 = SodexoInfo2Builder::init(
    'merchantContactPhone6'
)->build();
```

