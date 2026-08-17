
# Transaction Rule Source

## Structure

`TransactionRuleSource`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | ID of the resource, when applicable. | getId(): ?string | setId(?string id): void |
| `type` | `?string` | Optional | Indicates the type of resource for which the transaction rule is defined.<br><br>Possible values:<br><br>* **PaymentInstrumentGroup**<br><br>* **PaymentInstrument**<br><br>* **BalancePlatform**<br><br>* **EntityUsageConfiguration**<br><br>* **PlatformRule**: The transaction rule is a platform-wide rule imposed by Adyen. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRuleSourceBuilder;

$transactionRuleSource = TransactionRuleSourceBuilder::init()
    ->id('id4')
    ->type('type4')
    ->build();
```

