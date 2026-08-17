
# Risk Scores Restriction

## Structure

`RiskScoresRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?RiskScores`](../../doc/models/risk-scores.md) | Optional | - | getValue(): ?RiskScores | setValue(?RiskScores value): void |

## Example

```php
use AdyenLib\Models\Builders\RiskScoresRestrictionBuilder;
use AdyenLib\Models\Builders\RiskScoresBuilder;

$riskScoresRestriction = RiskScoresRestrictionBuilder::init(
    'operation8'
)
    ->value(
        RiskScoresBuilder::init()
            ->mastercard(84)
            ->visa(6)
            ->build()
    )
    ->build();
```

