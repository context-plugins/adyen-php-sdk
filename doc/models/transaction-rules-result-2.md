
# Transaction Rules Result 2

Contains the results of the evaluation of the transaction rules.

## Structure

`TransactionRulesResult2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `advice` | `?string` | Optional | The advice given by the Risk analysis. | getAdvice(): ?string | setAdvice(?string advice): void |
| `allHardBlockRulesPassed` | `?bool` | Optional | Indicates whether the transaction passed the evaluation for all hardblock rules | getAllHardBlockRulesPassed(): ?bool | setAllHardBlockRulesPassed(?bool allHardBlockRulesPassed): void |
| `score` | `?int` | Optional | The score of the Risk analysis. | getScore(): ?int | setScore(?int score): void |
| `triggeredTransactionRules` | [`?(TransactionEventViolation[])`](../../doc/models/transaction-event-violation.md) | Optional | Array containing all the transaction rules that the transaction triggered. | getTriggeredTransactionRules(): ?array | setTriggeredTransactionRules(?array triggeredTransactionRules): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRulesResult2Builder;
use AdyenLib\Models\Builders\TransactionEventViolationBuilder;
use AdyenLib\Models\Builders\TransactionRuleReference2Builder;
use AdyenLib\Models\Builders\TransactionRuleSource2Builder;

$transactionRulesResult2 = TransactionRulesResult2Builder::init()
    ->advice('advice4')
    ->allHardBlockRulesPassed(false)
    ->score(10)
    ->triggeredTransactionRules(
        [
            TransactionEventViolationBuilder::init()
                ->reason('reason6')
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
                ->build(),
            TransactionEventViolationBuilder::init()
                ->reason('reason6')
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
                ->build(),
            TransactionEventViolationBuilder::init()
                ->reason('reason6')
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
                ->build()
        ]
    )
    ->build();
```

