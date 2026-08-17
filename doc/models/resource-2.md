
# Resource 2

## Structure

`Resource2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\Resource2Builder;

$resource = Resource2Builder::init()
    ->type('Resource')
    ->build();
```

