
# Carnet Info 1

Details to provide if `type` is **carnet**.

## Structure

`CarnetInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addMccAcronym` | `?bool` | Optional | Indicates whether to add the MCC acronym to the merchant name for Prosa acquirer in Mexico.<br>When set to **true**, the MCC acronym is automatically appended to the merchant name.<br>Default: **false**. | getAddMccAcronym(): ?bool | setAddMccAcronym(?bool addMccAcronym): void |
| `transactionDescription` | [`?TransactionDescriptionInfo1`](../../doc/models/transaction-description-info-1.md) | Optional | Information regarding the transaction description.<br><br>> You cannot configure the transaction description in the test environment. | getTransactionDescription(): ?TransactionDescriptionInfo1 | setTransactionDescription(?TransactionDescriptionInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\CarnetInfo1Builder;
use AdyenLib\Models\Builders\TransactionDescriptionInfo1Builder;
use AdyenLib\Models\Type8Enum;

$carnetInfo1 = CarnetInfo1Builder::init()
    ->addMccAcronym(false)
    ->transactionDescription(
        TransactionDescriptionInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

