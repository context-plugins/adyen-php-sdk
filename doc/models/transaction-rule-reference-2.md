
# Transaction Rule Reference 2

Contains information about the transaction rule.

## Structure

`TransactionRuleReference2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The description of the resource. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the resource. | getId(): ?string | setId(?string id): void |
| `outcomeType` | `?string` | Optional | The outcome type of the rule. | getOutcomeType(): ?string | setOutcomeType(?string outcomeType): void |
| `reference` | `?string` | Optional | The reference for the resource. | getReference(): ?string | setReference(?string reference): void |
| `score` | `?int` | Optional | The transaction score determined by the rule. Returned only when `outcomeType` is **scoreBased**. | getScore(): ?int | setScore(?int score): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRuleReference2Builder;

$transactionRuleReference2 = TransactionRuleReference2Builder::init()
    ->description('description8')
    ->id('id2')
    ->outcomeType('outcomeType2')
    ->reference('reference2')
    ->score(200)
    ->build();
```

