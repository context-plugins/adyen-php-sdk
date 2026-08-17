
# External Reason 2

The external reason of this transfer.

## Structure

`ExternalReason2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The reason code. | getCode(): ?string | setCode(?string code): void |
| `description` | `?string` | Optional | The description of the reason code. | getDescription(): ?string | setDescription(?string description): void |
| `namespace` | `?string` | Optional | The namespace for the reason code. | getNamespace(): ?string | setNamespace(?string namespace): void |

## Example

```php
use AdyenLib\Models\Builders\ExternalReason2Builder;

$externalReason2 = ExternalReason2Builder::init()
    ->code('code2')
    ->description('description4')
    ->namespace('namespace8')
    ->build();
```

