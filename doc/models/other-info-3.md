
# Other Info 3

Additional information for raising a dispute of `type` **other**. Required for disputes of `type` **other**.

**Note:** The **other** dispute `type` is currently in beta testing. Do not create or submit any disputes for this dispute `type` at this time.

## Structure

`OtherInfo3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `descriptionOfIssue` | `string` | Required | Your description of the issue for raising a dispute of `type` **other**.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `2500` | getDescriptionOfIssue(): string | setDescriptionOfIssue(string descriptionOfIssue): void |
| `subType` | [`string(SubType11Enum)`](../../doc/models/sub-type-11-enum.md) | Required | The specific category of **other** dispute that you are raising.<br><br>Possible values: **atmDispute**, **cancelledGoodsServices**, **cancelledRecurring**, **counterfeit**, **creditNotProcessed**, **notAsDescribed**. | getSubType(): string | setSubType(string subType): void |
| `whatWasPurchased` | [`string(ProductType11Enum)`](../../doc/models/product-type-11-enum.md) | Required | The type of product that you purchased.<br><br>Possible values: **goods**, **services**. | getWhatWasPurchased(): string | setWhatWasPurchased(string whatWasPurchased): void |

## Example

```php
use AdyenLib\Models\Builders\OtherInfo3Builder;
use AdyenLib\Models\SubType11Enum;
use AdyenLib\Models\ProductType11Enum;

$otherInfo3 = OtherInfo3Builder::init(
    'descriptionOfIssue2',
    SubType11Enum::COUNTERFEIT,
    ProductType11Enum::GOODS
)->build();
```

