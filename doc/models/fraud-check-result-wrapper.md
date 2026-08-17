
# Fraud Check Result Wrapper

## Structure

`FraudCheckResultWrapper`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fraudCheckResult` | [`?FraudCheckResult`](../../doc/models/fraud-check-result.md) | Optional | - | getFraudCheckResult(): ?FraudCheckResult | setFraudCheckResult(?FraudCheckResult fraudCheckResult): void |

## Example

```php
use AdyenLib\Models\Builders\FraudCheckResultWrapperBuilder;
use AdyenLib\Models\Builders\FraudCheckResultBuilder;

$fraudCheckResultWrapper = FraudCheckResultWrapperBuilder::init()
    ->fraudCheckResult(
        FraudCheckResultBuilder::init(
            114,
            2,
            'name0'
        )->build()
    )->build();
```

