
# Sodexo Response Info

## Structure

`SodexoResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantContactPhone` | `?string` | Optional | Sodexo merchantContactPhone | getMerchantContactPhone(): ?string | setMerchantContactPhone(?string merchantContactPhone): void |

## Example

```php
use AdyenLib\Models\Builders\SodexoResponseInfoBuilder;

$sodexoResponseInfo = SodexoResponseInfoBuilder::init()
    ->merchantContactPhone('merchantContactPhone8')
    ->build();
```

