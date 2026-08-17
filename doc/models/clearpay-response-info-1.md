
# Clearpay Response Info 1

**clearpay** details

## Structure

`ClearpayResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supportUrl` | `?string` | Optional | Support Url | getSupportUrl(): ?string | setSupportUrl(?string supportUrl): void |

## Example

```php
use AdyenLib\Models\Builders\ClearpayResponseInfo1Builder;

$clearpayResponseInfo1 = ClearpayResponseInfo1Builder::init()
    ->supportUrl('supportUrl8')
    ->build();
```

