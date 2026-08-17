
# Confidence Score

## Structure

`ConfidenceScore`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | `?(string[])` | Optional | - | getErrors(): ?array | setErrors(?array errors): void |
| `score` | `?float` | Optional | - | getScore(): ?float | setScore(?float score): void |

## Example

```php
use AdyenLib\Models\Builders\ConfidenceScoreBuilder;

$confidenceScore = ConfidenceScoreBuilder::init()
    ->errors(
        [
            'errors9',
            'errors0',
            'errors1'
        ]
    )
    ->score(155.44)
    ->build();
```

