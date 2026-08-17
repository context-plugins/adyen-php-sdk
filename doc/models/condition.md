
# Condition

## Structure

`Condition`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceType` | [`string(BalanceTypeEnum)`](../../doc/models/balance-type-enum.md) | Required | Define the type of balance about which you want to get notified. Possible values:<br><br>* **available**: the balance available for use.<br><br>* **balance**: the sum of transactions that have already been settled.<br><br>* **pending**: the sum of transactions that will be settled in the future.<br><br>* **reserved**: the balance currently held in reserve. | getBalanceType(): string | setBalanceType(string balanceType): void |
| `conditionType` | [`string(ConditionTypeEnum)`](../../doc/models/condition-type-enum.md) | Required | Define when you want to get notified about a balance change. Possible values:<br><br>* **greaterThan**: the balance in the account(s) exceeds the specified `value`.<br><br>* **greaterThanOrEqual**: the balance in the account(s) reaches or exceeds the specified `value`.<br><br>* **lessThan**: the balance in the account(s) drops below the specified `value`.<br><br>* **lessThanOrEqual**: the balance in the account(s) reaches to drops below the specified `value`. | getConditionType(): string | setConditionType(string conditionType): void |
| `value` | `int` | Required | The value limit in the specified balance type and currency, in minor units. | getValue(): int | setValue(int value): void |

## Example

```php
use AdyenLib\Models\Builders\ConditionBuilder;
use AdyenLib\Models\BalanceTypeEnum;
use AdyenLib\Models\ConditionTypeEnum;

$condition = ConditionBuilder::init(
    BalanceTypeEnum::BALANCE,
    ConditionTypeEnum::LESSTHAN,
    194
)->build();
```

