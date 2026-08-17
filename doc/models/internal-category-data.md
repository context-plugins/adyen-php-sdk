
# Internal Category Data

## Structure

`InternalCategoryData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `modificationMerchantReference` | `?string` | Optional | The capture's merchant reference included in the transfer. | getModificationMerchantReference(): ?string | setModificationMerchantReference(?string modificationMerchantReference): void |
| `modificationPspReference` | `?string` | Optional | The capture reference included in the transfer. | getModificationPspReference(): ?string | setModificationPspReference(?string modificationPspReference): void |
| `type` | [`?string(Type411Enum)`](../../doc/models/type-411-enum.md) | Optional | **internal**<br><br>**Default**: `Type411Enum::INTERNAL` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\InternalCategoryDataBuilder;
use AdyenLib\Models\Type411Enum;

$internalCategoryData = InternalCategoryDataBuilder::init()
    ->modificationMerchantReference('modificationMerchantReference4')
    ->modificationPspReference('modificationPspReference6')
    ->type(Type411Enum::INTERNAL)
    ->build();
```

