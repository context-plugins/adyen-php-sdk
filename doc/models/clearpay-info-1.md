
# Clearpay Info 1

Details to provide if `type` is **clearpay**.

## Structure

`ClearpayInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supportUrl` | `string` | Required | Support Url | getSupportUrl(): string | setSupportUrl(string supportUrl): void |

## Example

```php
use AdyenLib\Models\Builders\ClearpayInfo1Builder;

$clearpayInfo1 = ClearpayInfo1Builder::init(
    'supportUrl0'
)->build();
```

