
# Affirm Response Info

## Structure

`AffirmResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `publicApiKey` | `?string` | Optional | Affirm public API key | getPublicApiKey(): ?string | setPublicApiKey(?string publicApiKey): void |

## Example

```php
use AdyenLib\Models\Builders\AffirmResponseInfoBuilder;

$affirmResponseInfo = AffirmResponseInfoBuilder::init()
    ->publicApiKey('publicApiKey8')
    ->build();
```

