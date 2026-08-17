
# Permit Restriction

## Structure

`PermitRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maxAmount` | [`?Amount`](../../doc/models/amount.md) | Optional | The total sum amount of one or more payments made using this permit may not exceed this amount if set. | getMaxAmount(): ?Amount | setMaxAmount(?Amount maxAmount): void |
| `singleTransactionLimit` | [`?Amount`](../../doc/models/amount.md) | Optional | The amount of any single payment using this permit may not exceed this amount if set. | getSingleTransactionLimit(): ?Amount | setSingleTransactionLimit(?Amount singleTransactionLimit): void |
| `singleUse` | `?bool` | Optional | Only a single payment can be made using this permit if set to true, otherwise multiple payments are allowed. | getSingleUse(): ?bool | setSingleUse(?bool singleUse): void |

## Example

```php
use AdyenLib\Models\Builders\PermitRestrictionBuilder;
use AdyenLib\Models\Builders\AmountBuilder;

$permitRestriction = PermitRestrictionBuilder::init()
    ->maxAmount(
        AmountBuilder::init(
            'currency4',
            160
        )->build()
    )
    ->singleTransactionLimit(
        AmountBuilder::init(
            'currency8',
            122
        )->build()
    )
    ->singleUse(false)
    ->build();
```

