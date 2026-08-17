
# Split Dcc

## Structure

`SplitDcc`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderPercentage` | `?int` | Optional | - | getAccountHolderPercentage(): ?int | setAccountHolderPercentage(?int accountHolderPercentage): void |

## Example

```php
use AdyenLib\Models\Builders\SplitDccBuilder;

$splitDcc = SplitDccBuilder::init()
    ->accountHolderPercentage(140)
    ->build();
```

