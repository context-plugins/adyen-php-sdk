
# Counterparty Bank Restriction

## Structure

`CounterpartyBankRestriction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(BankIdentification[])`](../../doc/models/bank-identification.md) | Optional | The list of counterparty bank institutions to be evaluated. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\CounterpartyBankRestrictionBuilder;
use AdyenLib\Models\Builders\BankIdentificationBuilder;
use AdyenLib\Models\IdentificationTypeEnum;

$counterpartyBankRestriction = CounterpartyBankRestrictionBuilder::init(
    'operation4'
)
    ->value(
        [
            BankIdentificationBuilder::init()
                ->country('country6')
                ->identification('identification0')
                ->identificationType(IdentificationTypeEnum::BIC)
                ->build()
        ]
    )
    ->build();
```

