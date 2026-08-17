
# Generic Pm with Tdi Info 9

Details to provide if `type` is **maestro_usa**.
Only for Maestro USA, otherwise use `maestro`.

## Structure

`GenericPmWithTdiInfo9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionDescription` | [`?TransactionDescriptionInfo1`](../../doc/models/transaction-description-info-1.md) | Optional | Information regarding the transaction description.<br><br>> You cannot configure the transaction description in the test environment. | getTransactionDescription(): ?TransactionDescriptionInfo1 | setTransactionDescription(?TransactionDescriptionInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\GenericPmWithTdiInfo9Builder;
use AdyenLib\Models\Builders\TransactionDescriptionInfo1Builder;
use AdyenLib\Models\Type8Enum;

$genericPmWithTdiInfo9 = GenericPmWithTdiInfo9Builder::init()
    ->transactionDescription(
        TransactionDescriptionInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

