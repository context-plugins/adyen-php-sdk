
# Patchable Top Up Amount 2

The currency and value to be added to the balance account, specified in minor units. This can be a fixed amount or a target amount.

## Structure

`PatchableTopUpAmount2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fixed` | [PatchableAmountDTO](../../doc/models/patchable-amount-dto.md)\|null | Optional | This is a container for one-of cases. | getFixed(): ?PatchableAmountDTO | setFixed(?PatchableAmountDTO fixed): void |
| `target` | [PatchableAmountDTO](../../doc/models/patchable-amount-dto.md)\|null | Optional | This is a container for one-of cases. | getTarget(): ?PatchableAmountDTO | setTarget(?PatchableAmountDTO target): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableTopUpAmount2Builder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;

$patchableTopUpAmount2 = PatchableTopUpAmount2Builder::init()
    ->fixed(
        PatchableAmountDTOBuilder::init()
            ->currency('currency2')
            ->value(164)
            ->build()
    )
    ->target(
        PatchableAmountDTOBuilder::init()
            ->currency('currency2')
            ->value(164)
            ->build()
    )
    ->build();
```

