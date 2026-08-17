
# Affirm Response Info 1

*affirm** details

## Structure

`AffirmResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `publicApiKey` | `?string` | Optional | Affirm public API key | getPublicApiKey(): ?string | setPublicApiKey(?string publicApiKey): void |

## Example

```php
use AdyenLib\Models\Builders\AffirmResponseInfo1Builder;

$affirmResponseInfo1 = AffirmResponseInfo1Builder::init()
    ->publicApiKey('publicApiKey6')
    ->build();
```

