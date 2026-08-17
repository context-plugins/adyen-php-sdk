
# Permit Result

## Structure

`PermitResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `resultKey` | `?string` | Optional | The key to link permit requests to permit results. | getResultKey(): ?string | setResultKey(?string resultKey): void |
| `token` | `?string` | Optional | The permit token which is used to make payments by the partner company. | getToken(): ?string | setToken(?string token): void |

## Example

```php
use AdyenLib\Models\Builders\PermitResultBuilder;

$permitResult = PermitResultBuilder::init()
    ->resultKey('resultKey4')
    ->token('token6')
    ->build();
```

