
# Financier

## Structure

`Financier`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`PatchableAmountDTO`](../../doc/models/patchable-amount-dto.md) | Required | The amount of the funds the financier provided. | getAmount(): PatchableAmountDTO | setAmount(PatchableAmountDTO amount): void |
| `firstName` | `string` | Required | The financier's first name. | getFirstName(): string | setFirstName(string firstName): void |
| `lastName` | `string` | Required | The financier's last name. | getLastName(): string | setLastName(string lastName): void |
| `location` | `string` | Required | The city and country/region where the financier is currently located. For example: Chicago, USA | getLocation(): string | setLocation(string location): void |

## Example

```php
use AdyenLib\Models\Builders\FinancierBuilder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;

$financier = FinancierBuilder::init(
    PatchableAmountDTOBuilder::init()
        ->currency('currency2')
        ->value(110)
        ->build(),
    'firstName0',
    'lastName8',
    'location8'
)->build();
```

