
# Field Type

The type of error field.

## Structure

`FieldType`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `field` | `?string` | Optional | The full name of the property. | getField(): ?string | setField(?string field): void |
| `fieldName` | [`?string(FieldNameEnum)`](../../doc/models/field-name-enum.md) | Optional | The type of the field. | getFieldName(): ?string | setFieldName(?string fieldName): void |
| `shareholderCode` | `?string` | Optional | The code of the shareholder that the field belongs to. If empty, the field belongs to an account holder. | getShareholderCode(): ?string | setShareholderCode(?string shareholderCode): void |

## Example

```php
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$fieldType = FieldTypeBuilder::init()
    ->field('field6')
    ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
    ->shareholderCode('shareholderCode0')
    ->build();
```

