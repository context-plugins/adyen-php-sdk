
# Patchable Other Info

## Structure

`PatchableOtherInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `descriptionOfIssue` | `?string` | Optional | Your description of the issue for raising a dispute of `type` **other**.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `2500` | getDescriptionOfIssue(): ?string | setDescriptionOfIssue(?string descriptionOfIssue): void |
| `subType` | [`?string(SubType11Enum)`](../../doc/models/sub-type-11-enum.md) | Optional | The specific category of **other** dispute that you are raising.<br><br>Possible values: **atmDispute**, **cancelledGoodsServices**, **cancelledRecurring**, **counterfeit**, **creditNotProcessed**, **notAsDescribed**. | getSubType(): ?string | setSubType(?string subType): void |
| `whatWasPurchased` | [`?string(ProductType11Enum)`](../../doc/models/product-type-11-enum.md) | Optional | The type of product that you purchased.<br><br>Possible values: **goods**, **services**. | getWhatWasPurchased(): ?string | setWhatWasPurchased(?string whatWasPurchased): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableOtherInfoBuilder;
use AdyenLib\Models\SubType11Enum;
use AdyenLib\Models\ProductType11Enum;

$patchableOtherInfo = PatchableOtherInfoBuilder::init()
    ->descriptionOfIssue('descriptionOfIssue2')
    ->subType(SubType11Enum::COUNTERFEIT)
    ->whatWasPurchased(ProductType11Enum::GOODS)
    ->build();
```

