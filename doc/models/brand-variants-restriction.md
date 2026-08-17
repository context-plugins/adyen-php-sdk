
# Brand Variants Restriction

## Structure

`BrandVariantsRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | `?(string[])` | Optional | List of card brand variants.<br><br>Possible values:<br><br>- **mc**, **mccredit**, **mccommercialcredit_b2b**, **mcdebit**, **mcbusinessdebit**, **mcbusinessworlddebit**, **mcprepaid**, **mcmaestro**<br><br>- **visa**, **visacredit**, **visadebit**, **visaprepaid**.<br><br>You can specify a rule for a generic variant. For example, to create a rule for all Mastercard payment instruments, use **mc**. The rule is applied to all payment instruments under **mc**, such as **mcbusinessdebit** and **mcdebit**. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\BrandVariantsRestrictionBuilder;

$brandVariantsRestriction = BrandVariantsRestrictionBuilder::init(
    'operation4'
)
    ->value(
        [
            'value8',
            'value9',
            'value0'
        ]
    )
    ->build();
```

