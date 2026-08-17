
# Merchant Names Restriction

## Structure

`MerchantNamesRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(StringMatch[])`](../../doc/models/string-match.md) | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantNamesRestrictionBuilder;
use AdyenLib\Models\Builders\StringMatchBuilder;
use AdyenLib\Models\OperationEnum;

$merchantNamesRestriction = MerchantNamesRestrictionBuilder::init(
    'operation0'
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

