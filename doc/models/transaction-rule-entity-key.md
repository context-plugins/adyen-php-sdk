
# Transaction Rule Entity Key

## Structure

`TransactionRuleEntityKey`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `entityReference` | `?string` | Optional | The unique identifier of the resource. | getEntityReference(): ?string | setEntityReference(?string entityReference): void |
| `entityType` | `?string` | Optional | The type of resource.<br><br>Possible values: **balancePlatform**, **paymentInstrumentGroup**, **accountHolder**, **balanceAccount**, or **paymentInstrument**. | getEntityType(): ?string | setEntityType(?string entityType): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRuleEntityKeyBuilder;

$transactionRuleEntityKey = TransactionRuleEntityKeyBuilder::init()
    ->entityReference('entityReference2')
    ->entityType('entityType0')
    ->build();
```

