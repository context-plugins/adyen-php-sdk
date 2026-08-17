
# Processing Types Restriction

## Structure

`ProcessingTypesRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value4Enum)[])`](../../doc/models/value-4-enum.md) | Optional | List of processing types.<br><br>Possible values: **atmWithdraw**, **balanceInquiry**, **ecommerce**, **moto**, **pos**, **recurring**, **token**. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\ProcessingTypesRestrictionBuilder;
use AdyenLib\Models\Value4Enum;

$processingTypesRestriction = ProcessingTypesRestrictionBuilder::init(
    'operation6'
)
    ->value(
        [
            Value4Enum::POS,
            Value4Enum::RECURRING
        ]
    )
    ->build();
```

