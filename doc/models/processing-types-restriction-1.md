
# Processing Types Restriction 1

List of processing types and the operation.

Supported operations: **anyMatch**, **noneMatch**.

## Structure

`ProcessingTypesRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(string(Value4Enum)[])`](../../doc/models/value-4-enum.md) | Optional | List of processing types.<br><br>Possible values: **atmWithdraw**, **balanceInquiry**, **ecommerce**, **moto**, **pos**, **recurring**, **token**. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\ProcessingTypesRestriction1Builder;
use AdyenLib\Models\Value4Enum;

$processingTypesRestriction1 = ProcessingTypesRestriction1Builder::init(
    'operation2'
)
    ->value(
        [
            Value4Enum::ECOMMERCE,
            Value4Enum::MOTO
        ]
    )
    ->build();
```

