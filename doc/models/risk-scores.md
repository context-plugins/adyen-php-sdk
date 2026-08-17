
# Risk Scores

## Structure

`RiskScores`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `mastercard` | `?int` | Optional | Transaction risk score provided by Mastercard. Values provided by Mastercard range between 0 (lowest risk) to 998 (highest risk). | getMastercard(): ?int | setMastercard(?int mastercard): void |
| `visa` | `?int` | Optional | Transaction risk score provided by Visa. Values provided by Visa range between 01 (lowest risk) to 99 (highest risk). | getVisa(): ?int | setVisa(?int visa): void |

## Example

```php
use AdyenLib\Models\Builders\RiskScoresBuilder;

$riskScores = RiskScoresBuilder::init()
    ->mastercard(2)
    ->visa(180)
    ->build();
```

