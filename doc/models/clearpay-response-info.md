
# Clearpay Response Info

## Structure

`ClearpayResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supportUrl` | `?string` | Optional | Support Url | getSupportUrl(): ?string | setSupportUrl(?string supportUrl): void |

## Example

```php
use AdyenLib\Models\Builders\ClearpayResponseInfoBuilder;

$clearpayResponseInfo = ClearpayResponseInfoBuilder::init()
    ->supportUrl('supportUrl2')
    ->build();
```

