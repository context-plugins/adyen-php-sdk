
# Pay by Bank Plaid Update Info 1

Details to provide if `type` is **paybybank_plaid**.

## Structure

`PayByBankPlaidUpdateInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionDescription` | [`?TransactionDescriptionInfo1`](../../doc/models/transaction-description-info-1.md) | Optional | Information regarding the transaction description.<br><br>> You cannot configure the transaction description in the test environment. | getTransactionDescription(): ?TransactionDescriptionInfo1 | setTransactionDescription(?TransactionDescriptionInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\PayByBankPlaidUpdateInfo1Builder;
use AdyenLib\Models\Builders\TransactionDescriptionInfo1Builder;
use AdyenLib\Models\Type8Enum;

$payByBankPlaidUpdateInfo1 = PayByBankPlaidUpdateInfo1Builder::init()
    ->transactionDescription(
        TransactionDescriptionInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

