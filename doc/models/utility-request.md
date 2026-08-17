
# Utility Request

## Structure

`UtilityRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `originDomains` | `string[]` | Required | The list of origin domains, for which origin keys are requested. | getOriginDomains(): array | setOriginDomains(array originDomains): void |

## Example

```php
use AdyenLib\Models\Builders\UtilityRequestBuilder;

$utilityRequest = UtilityRequestBuilder::init(
    [
        'originDomains2',
        'originDomains3',
        'originDomains4'
    ]
)->build();
```

