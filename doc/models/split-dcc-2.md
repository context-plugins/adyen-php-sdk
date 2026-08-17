
# Split Dcc 2

Defines the logic for booking the markup paid by the customer for Dynamic Currency Conversion (DCC).

> This field is in pilot phase, and not yet available for all platforms.

## Structure

`SplitDcc2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderPercentage` | `?int` | Optional | - | getAccountHolderPercentage(): ?int | setAccountHolderPercentage(?int accountHolderPercentage): void |

## Example

```php
use AdyenLib\Models\Builders\SplitDcc2Builder;

$splitDcc2 = SplitDcc2Builder::init()
    ->accountHolderPercentage(198)
    ->build();
```

