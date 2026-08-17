
# Clearpay Info

## Structure

`ClearpayInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supportUrl` | `string` | Required | Support Url | getSupportUrl(): string | setSupportUrl(string supportUrl): void |

## Example

```php
use AdyenLib\Models\Builders\ClearpayInfoBuilder;

$clearpayInfo = ClearpayInfoBuilder::init(
    'supportUrl2'
)->build();
```

