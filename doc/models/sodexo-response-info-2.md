
# Sodexo Response Info 2

**sodexo** details

## Structure

`SodexoResponseInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantContactPhone` | `?string` | Optional | Sodexo merchantContactPhone | getMerchantContactPhone(): ?string | setMerchantContactPhone(?string merchantContactPhone): void |

## Example

```php
use AdyenLib\Models\Builders\SodexoResponseInfo2Builder;

$sodexoResponseInfo2 = SodexoResponseInfo2Builder::init()
    ->merchantContactPhone('merchantContactPhone0')
    ->build();
```

