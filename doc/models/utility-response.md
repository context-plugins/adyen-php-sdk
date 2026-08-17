
# Utility Response

## Structure

`UtilityResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `originKeys` | `?array<string,string>` | Optional | The list of origin keys for all requested domains. For each list item, the key is the domain and the value is the origin key. | getOriginKeys(): ?array | setOriginKeys(?array originKeys): void |

## Example

```php
use AdyenLib\Models\Builders\UtilityResponseBuilder;

$utilityResponse = UtilityResponseBuilder::init()
    ->originKeys(
        [
            'key0' => 'originKeys0'
        ]
    )
    ->build();
```

