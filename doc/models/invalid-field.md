
# Invalid Field

## Structure

`InvalidField`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `string` | Required | The field that has an invalid value. | getName(): string | setName(string name): void |
| `value` | `string` | Required | The invalid value. | getValue(): string | setValue(string value): void |
| `message` | `string` | Required | Description of the validation error. | getMessage(): string | setMessage(string message): void |

## Example

```php
use AdyenLib\Models\Builders\InvalidFieldBuilder;

$invalidField = InvalidFieldBuilder::init(
    'name6',
    'value8',
    'message6'
)->build();
```

