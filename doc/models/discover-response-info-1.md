
# Discover Response Info 1

**discover**. details

## Structure

`DiscoverResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionDescription` | [`?TransactionDescriptionResponseInfo1`](../../doc/models/transaction-description-response-info-1.md) | Optional | Information regarding the transaction description. | getTransactionDescription(): ?TransactionDescriptionResponseInfo1 | setTransactionDescription(?TransactionDescriptionResponseInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\DiscoverResponseInfo1Builder;
use AdyenLib\Models\Builders\TransactionDescriptionResponseInfo1Builder;
use AdyenLib\Models\Type8Enum;

$discoverResponseInfo1 = DiscoverResponseInfo1Builder::init()
    ->transactionDescription(
        TransactionDescriptionResponseInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

