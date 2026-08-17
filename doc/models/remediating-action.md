
# Remediating Action

## Structure

`RemediatingAction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The remediating action code. | getCode(): ?string | setCode(?string code): void |
| `message` | `?string` | Optional | A description of how you can resolve the verification error. | getMessage(): ?string | setMessage(?string message): void |

## Example

```php
use AdyenLib\Models\Builders\RemediatingActionBuilder;

$remediatingAction = RemediatingActionBuilder::init()
    ->code('code6')
    ->message('message8')
    ->build();
```

