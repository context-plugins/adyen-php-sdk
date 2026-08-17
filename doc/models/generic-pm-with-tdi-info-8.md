
# Generic Pm with Tdi Info 8

Details to provide if `type` is **maestro**.
In the US, `maestro` is not supported; use `maestro_usa` instead.

## Structure

`GenericPmWithTdiInfo8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionDescription` | [`?TransactionDescriptionInfo1`](../../doc/models/transaction-description-info-1.md) | Optional | Information regarding the transaction description.<br><br>> You cannot configure the transaction description in the test environment. | getTransactionDescription(): ?TransactionDescriptionInfo1 | setTransactionDescription(?TransactionDescriptionInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\GenericPmWithTdiInfo8Builder;
use AdyenLib\Models\Builders\TransactionDescriptionInfo1Builder;
use AdyenLib\Models\Type8Enum;

$genericPmWithTdiInfo8 = GenericPmWithTdiInfo8Builder::init()
    ->transactionDescription(
        TransactionDescriptionInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

