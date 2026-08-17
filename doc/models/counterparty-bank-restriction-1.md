
# Counterparty Bank Restriction 1

Contains a list of counterparty financial institutions and how they must be evaluated.

Supported operations: **anyMatch**, **noneMatch**.

## Structure

`CounterpartyBankRestriction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operation` | `string` | Required | Defines how the condition must be evaluated. | getOperation(): string | setOperation(string operation): void |
| `value` | [`?(BankIdentification[])`](../../doc/models/bank-identification.md) | Optional | The list of counterparty bank institutions to be evaluated. | getValue(): ?array | setValue(?array value): void |

## Example

```php
use AdyenLib\Models\Builders\CounterpartyBankRestriction1Builder;
use AdyenLib\Models\Builders\BankIdentificationBuilder;
use AdyenLib\Models\IdentificationTypeEnum;

$counterpartyBankRestriction1 = CounterpartyBankRestriction1Builder::init(
    'operation2'
)
    ->value(
        [
            BankIdentificationBuilder::init()
                ->country('country6')
                ->identification('identification0')
                ->identificationType(IdentificationTypeEnum::BIC)
                ->build(),
            BankIdentificationBuilder::init()
                ->country('country6')
                ->identification('identification0')
                ->identificationType(IdentificationTypeEnum::BIC)
                ->build(),
            BankIdentificationBuilder::init()
                ->country('country6')
                ->identification('identification0')
                ->identificationType(IdentificationTypeEnum::BIC)
                ->build()
        ]
    )
    ->build();
```

