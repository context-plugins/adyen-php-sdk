
# ICC Reset Data

## Structure

`ICCResetData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `aTRValue` | `?string` | Optional | **Constraints**: *Pattern*: `^.{1,100}$` | getATRValue(): ?string | setATRValue(?string aTRValue): void |
| `cardStatusWords` | `?string` | Optional | **Constraints**: *Pattern*: `^.{2,2}$` | getCardStatusWords(): ?string | setCardStatusWords(?string cardStatusWords): void |

## Example

```php
use AdyenLib\Models\Builders\ICCResetDataBuilder;

$iCCResetData = ICCResetDataBuilder::init()
    ->aTRValue('ATRValue2')
    ->cardStatusWords('CardStatusWords2')
    ->build();
```

