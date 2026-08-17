
# Create Permit Result

## Structure

`CreatePermitResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `permitResultList` | [`?(PermitResult[])`](../../doc/models/permit-result.md) | Optional | List of new permits. | getPermitResultList(): ?array | setPermitResultList(?array permitResultList): void |
| `pspReference` | `?string` | Optional | A unique reference associated with the request. This value is globally unique; quote it when communicating with us about this request. | getPspReference(): ?string | setPspReference(?string pspReference): void |

## Example

```php
use AdyenLib\Models\Builders\CreatePermitResultBuilder;
use AdyenLib\Models\Builders\PermitResultBuilder;

$createPermitResult = CreatePermitResultBuilder::init()
    ->permitResultList(
        [
            PermitResultBuilder::init()
                ->resultKey('resultKey4')
                ->token('token6')
                ->build(),
            PermitResultBuilder::init()
                ->resultKey('resultKey4')
                ->token('token6')
                ->build()
        ]
    )
    ->pspReference('pspReference0')
    ->build();
```

