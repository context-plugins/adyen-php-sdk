
# Entry Modes Restriction 1

List of point-of-sale entry modes and the operation..

Supported operations: **anyMatch**, **noneMatch**.

## Structure

`EntryModesRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value2Enum)[])`](../../doc/models/value-2-enum.md) | Optional | List of point-of-sale entry modes.<br><br>Possible values: **barcode**, **chip**, **cof**, **contactless**, **magstripe**, **manual**, **ocr**, **server**. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\EntryModesRestriction1Builder;
use AdyenLib\Models\Value2Enum;

$entryModesRestriction1 = EntryModesRestriction1Builder::init(
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

