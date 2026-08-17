
# Subject Erasure Response

## Structure

`SubjectErasureResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `result` | [`?string(Result2Enum)`](../../doc/models/result-2-enum.md) | Optional | The result of this operation. | getResult(): ?string | setResult(?string result): void |

## Example

```php
use AdyenLib\Models\Builders\SubjectErasureResponseBuilder;
use AdyenLib\Models\Result2Enum;

$subjectErasureResponse = SubjectErasureResponseBuilder::init()
    ->result(Result2Enum::PAYMENT_NOT_FOUND)
    ->build();
```

