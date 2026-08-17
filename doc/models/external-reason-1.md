
# External Reason 1

The external reason for the transfer status.

## Structure

`ExternalReason1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The reason code. | getCode(): ?string | setCode(?string code): void |
| `description` | `?string` | Optional | The description of the reason code. | getDescription(): ?string | setDescription(?string description): void |
| `namespace` | `?string` | Optional | The namespace for the reason code. | getNamespace(): ?string | setNamespace(?string namespace): void |

## Example

```php
use AdyenLib\Models\Builders\ExternalReason1Builder;

$externalReason1 = ExternalReason1Builder::init()
    ->code('code4')
    ->description('description6')
    ->namespace('namespace6')
    ->build();
```

