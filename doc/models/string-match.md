
# String Match

## Structure

`StringMatch`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | [`?string(OperationEnum)`](../../doc/models/operation-enum.md) | Optional | The type of string matching operation. Possible values:  **startsWith**, **endsWith**, **isEqualTo**, **contains**, | getOperation(): ?string | setOperation(?string operation): void |
| `value` | `?string` | Optional | The string to be matched. | getValue(): ?string | setValue(?string value): void |

## Example

```php
use AdyenLib\Models\Builders\StringMatchBuilder;
use AdyenLib\Models\OperationEnum;

$stringMatch = StringMatchBuilder::init()
    ->operation(OperationEnum::ISEQUALTO)
    ->value('value0')
    ->build();
```

