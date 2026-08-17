
# External Platform

Third-party developed platform used to initiate payment requests. For example, Magento, Zuora, etc.

## Structure

`ExternalPlatform`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `integrator` | `?string` | Optional | External platform integrator. | getIntegrator(): ?string | setIntegrator(?string integrator): void |
| `name` | `?string` | Optional | Name of the field. For example, Name of External Platform. | getName(): ?string | setName(?string name): void |
| `version` | `?string` | Optional | Version of the field. For example, Version of External Platform. | getVersion(): ?string | setVersion(?string version): void |

## Example

```php
use AdyenLib\Models\Builders\ExternalPlatformBuilder;

$externalPlatform = ExternalPlatformBuilder::init()
    ->integrator('integrator0')
    ->name('name4')
    ->version('version0')
    ->build();
```

