
# Register SCA Final Response

## Structure

`RegisterSCAFinalResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `success` | `?bool` | Optional | Specifies if the registration was initiated successfully. | getSuccess(): ?bool | setSuccess(?bool success): void |

## Example

```php
use AdyenLib\Models\Builders\RegisterSCAFinalResponseBuilder;

$registerSCAFinalResponse = RegisterSCAFinalResponseBuilder::init()
    ->success(false)
    ->build();
```

