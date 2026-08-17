
# Disable Permit Result

## Structure

`DisablePermitResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pspReference` | `?string` | Optional | A unique reference associated with the request. This value is globally unique; quote it when communicating with us about this request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `status` | `?string` | Optional | Status of the disable request. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\DisablePermitResultBuilder;

$disablePermitResult = DisablePermitResultBuilder::init()
    ->pspReference('pspReference8')
    ->status('status8')
    ->build();
```

