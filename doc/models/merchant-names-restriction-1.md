
# Merchant Names Restriction 1

List of names that will be compared to the merchant name according to the matching type.

Supported operations: **anyMatch**, **noneMatch**.

## Structure

`MerchantNamesRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(StringMatch[])`](../../doc/models/string-match.md) | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantNamesRestriction1Builder;
use AdyenLib\Models\Builders\StringMatchBuilder;
use AdyenLib\Models\OperationEnum;

$merchantNamesRestriction1 = MerchantNamesRestriction1Builder::init(
    'operation4'
)
    ->value(
        [
            StringMatchBuilder::init()
                ->operation(OperationEnum::ISEQUALTO)
                ->value('value4')
                ->build(),
            StringMatchBuilder::init()
                ->operation(OperationEnum::ISEQUALTO)
                ->value('value4')
                ->build(),
            StringMatchBuilder::init()
                ->operation(OperationEnum::ISEQUALTO)
                ->value('value4')
                ->build()
        ]
    )
    ->build();
```

