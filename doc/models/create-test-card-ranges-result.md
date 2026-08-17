
# Create Test Card Ranges Result

## Structure

`CreateTestCardRangesResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `rangeCreationResults` | [`TestCardRangeCreationResult[]`](../../doc/models/test-card-range-creation-result.md) | Required | The results of the test card creation. | getRangeCreationResults(): array | setRangeCreationResults(array rangeCreationResults): void |

## Example

```php
use AdyenLib\Models\Builders\CreateTestCardRangesResultBuilder;
use AdyenLib\Models\Builders\TestCardRangeCreationResultBuilder;
use AdyenLib\Models\CreationResultCodeEnum;

$createTestCardRangesResult = CreateTestCardRangesResultBuilder::init(
    [
        TestCardRangeCreationResultBuilder::init(
            'cardNumberRangeEnd6',
            'cardNumberRangeStart8',
            CreationResultCodeEnum::ALREADY_EXISTS
        )
            ->message('message0')
            ->build()
    ]
)->build();
```

