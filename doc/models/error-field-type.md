
# Error Field Type

## Structure

`ErrorFieldType`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errorCode` | `?int` | Optional | The validation error code. | getErrorCode(): ?int | setErrorCode(?int errorCode): void |
| `errorDescription` | `?string` | Optional | A description of the validation error. | getErrorDescription(): ?string | setErrorDescription(?string errorDescription): void |
| `fieldType` | [`?FieldType`](../../doc/models/field-type.md) | Optional | The type of error field. | getFieldType(): ?FieldType | setFieldType(?FieldType fieldType): void |

## Example

```php
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$errorFieldType = ErrorFieldTypeBuilder::init()
    ->errorCode(124)
    ->errorDescription('errorDescription2')
    ->fieldType(
        FieldTypeBuilder::init()
            ->field('field6')
            ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
            ->shareholderCode('shareholderCode0')
            ->build()
    )
    ->build();
```

