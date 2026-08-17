
# Countries Restriction

## Structure

`CountriesRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?(string[])` | Optional | List of two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country codes. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\CountriesRestrictionBuilder;

$countriesRestriction = CountriesRestrictionBuilder::init(
    'operation6'
)
    ->value(
        [
            'value0',
            'value1',
            'value2'
        ]
    )
    ->build();
```

