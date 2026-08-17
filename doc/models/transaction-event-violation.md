
# Transaction Event Violation

## Structure

`TransactionEventViolation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | An explanation about why the transaction rule failed. | getReason(): ?string | setReason(?string reason): void |
| `transactionRule` | [`?TransactionRuleReference2`](../../doc/models/transaction-rule-reference-2.md) | Optional | Contains information about the transaction rule. | getTransactionRule(): ?TransactionRuleReference2 | setTransactionRule(?TransactionRuleReference2 transactionRule): void |
| `transactionRuleSource` | [`?TransactionRuleSource2`](../../doc/models/transaction-rule-source-2.md) | Optional | Contains information about the resource to which the transaction rule applies. | getTransactionRuleSource(): ?TransactionRuleSource2 | setTransactionRuleSource(?TransactionRuleSource2 transactionRuleSource): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionEventViolationBuilder;
use AdyenLib\Models\Builders\TransactionRuleReference2Builder;
use AdyenLib\Models\Builders\TransactionRuleSource2Builder;

$transactionEventViolation = TransactionEventViolationBuilder::init()
    ->reason('reason8')
    ->transactionRule(
        TransactionRuleReference2Builder::init()
            ->description('description2')
            ->id('id2')
            ->outcomeType('outcomeType8')
            ->reference('reference2')
            ->score(68)
            ->build()
    )
    ->transactionRuleSource(
        TransactionRuleSource2Builder::init()
            ->id('id4')
            ->type('type4')
            ->build()
    )
    ->build();
```

