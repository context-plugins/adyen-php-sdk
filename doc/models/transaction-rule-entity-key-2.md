
# Transaction Rule Entity Key 2

The type and unique identifier of the resource to which the rule applies.

## Structure

`TransactionRuleEntityKey2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entityReference` | `?string` | Optional | The unique identifier of the resource. | getEntityReference(): ?string | setEntityReference(?string entityReference): void |
| `entityType` | `?string` | Optional | The type of resource.<br><br>Possible values: **balancePlatform**, **paymentInstrumentGroup**, **accountHolder**, **balanceAccount**, or **paymentInstrument**. | getEntityType(): ?string | setEntityType(?string entityType): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRuleEntityKey2Builder;

$transactionRuleEntityKey2 = TransactionRuleEntityKey2Builder::init()
    ->entityReference('entityReference8')
    ->entityType('entityType4')
    ->build();
```

