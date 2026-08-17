
# Risk Scores Restriction 1

Risk scores provided by specific sources. The same operation applies to all scores.

Current sources available: **visa**, **mastercard**

Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**.

## Structure

`RiskScoresRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?RiskScores`](../../doc/models/risk-scores.md) | Optional | - | getValue(): ?RiskScores | setValue(?RiskScores value): void |

## Example

```php
use AdyenLib\Models\Builders\RiskScoresRestriction1Builder;
use AdyenLib\Models\Builders\RiskScoresBuilder;

$riskScoresRestriction1 = RiskScoresRestriction1Builder::init(
    'operation0'
)
    ->value(
        RiskScoresBuilder::init()
            ->mastercard(84)
            ->visa(6)
            ->build()
    )
    ->build();
```

