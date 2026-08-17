
# Entry Modes Restriction

## Structure

`EntryModesRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value2Enum)[])`](../../doc/models/value-2-enum.md) | Optional | List of point-of-sale entry modes.<br><br>Possible values: **barcode**, **chip**, **cof**, **contactless**, **magstripe**, **manual**, **ocr**, **server**. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\EntryModesRestrictionBuilder;
use AdyenLib\Models\Value2Enum;

$entryModesRestriction = EntryModesRestrictionBuilder::init(
    'operation4'
)
    ->value(
        [
            Value2Enum::MAGSTRIPE,
            Value2Enum::MANUAL,
            Value2Enum::OCR
        ]
    )
    ->build();
```

