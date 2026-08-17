
# Patchable Top Up Amount

## Structure

`PatchableTopUpAmount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fixed` | [PatchableAmountDTO](../../doc/models/patchable-amount-dto.md)\|null | Optional | This is a container for one-of cases. | getFixed(): ?PatchableAmountDTO | setFixed(?PatchableAmountDTO fixed): void |
| `target` | [PatchableAmountDTO](../../doc/models/patchable-amount-dto.md)\|null | Optional | This is a container for one-of cases. | getTarget(): ?PatchableAmountDTO | setTarget(?PatchableAmountDTO target): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableTopUpAmountBuilder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;

$patchableTopUpAmount = PatchableTopUpAmountBuilder::init()
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

