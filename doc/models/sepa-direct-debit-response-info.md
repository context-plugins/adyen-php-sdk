
# Sepa Direct Debit Response Info

## Structure

`SepaDirectDebitResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `creditorId` | `?string` | Optional | Creditor id | getCreditorId(): ?string | setCreditorId(?string creditorId): void |
| `transactionDescription` | [`?TransactionDescriptionResponseInfo1`](../../doc/models/transaction-description-response-info-1.md) | Optional | Information regarding the transaction description. | getTransactionDescription(): ?TransactionDescriptionResponseInfo1 | setTransactionDescription(?TransactionDescriptionResponseInfo1 transactionDescription): void |

## Example

```php
use AdyenLib\Models\Builders\SepaDirectDebitResponseInfoBuilder;
use AdyenLib\Models\Builders\TransactionDescriptionResponseInfo1Builder;
use AdyenLib\Models\Type8Enum;

$sepaDirectDebitResponseInfo = SepaDirectDebitResponseInfoBuilder::init()
    ->creditorId('creditorId2')
    ->transactionDescription(
        TransactionDescriptionResponseInfo1Builder::init()
            ->doingBusinessAsName('doingBusinessAsName0')
            ->type(Type8Enum::FIXED)
            ->build()
    )
    ->build();
```

