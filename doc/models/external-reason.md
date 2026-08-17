
# External Reason

## Structure

`ExternalReason`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The reason code. | getCode(): ?string | setCode(?string code): void |
| `description` | `?string` | Optional | The description of the reason code. | getDescription(): ?string | setDescription(?string description): void |
| `namespace` | `?string` | Optional | The namespace for the reason code. | getNamespace(): ?string | setNamespace(?string namespace): void |

## Example

```php
use AdyenLib\Models\Builders\ExternalReasonBuilder;

$externalReason = ExternalReasonBuilder::init()
    ->code('code6')
    ->description('description8')
    ->namespace('namespace4')
    ->build();
```

