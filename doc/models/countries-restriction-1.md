
# Countries Restriction 1

List of countries and the operation.

Supported operations: **anyMatch**, **noneMatch**.

## Structure

`CountriesRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?(string[])` | Optional | List of two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country codes. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\CountriesRestriction1Builder;

$countriesRestriction1 = CountriesRestriction1Builder::init(
    'operation0'
)
    ->value(
        [
            'value4',
            'value5',
            'value6'
        ]
    )
    ->build();
```

