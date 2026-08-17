
# Transaction Rule Response

## Structure

`TransactionRuleResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionRule` | [`?TransactionRule1`](../../doc/models/transaction-rule-1.md) | Optional | The transaction rule. | getTransactionRule(): ?TransactionRule1 | setTransactionRule(?TransactionRule1 transactionRule): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRuleResponseBuilder;
use AdyenLib\Models\Builders\TransactionRule1Builder;
use AdyenLib\Models\Builders\TransactionRuleEntityKey2Builder;
use AdyenLib\Models\Builders\TransactionRuleInterval1Builder;
use AdyenLib\Models\Type131Enum;
use AdyenLib\Models\DayOfWeekEnum;
use AdyenLib\Models\Builders\Duration1Builder;
use AdyenLib\Models\UnitEnum;
use AdyenLib\Models\Builders\TransactionRuleRestrictions1Builder;
use AdyenLib\Models\Builders\ActiveNetworkTokensRestriction1Builder;
use AdyenLib\Models\Builders\BrandVariantsRestriction1Builder;
use AdyenLib\Models\Builders\CounterpartyBankRestriction1Builder;
use AdyenLib\Models\Builders\BankIdentificationBuilder;
use AdyenLib\Models\IdentificationTypeEnum;
use AdyenLib\Models\Builders\CounterpartyTypesRestriction1Builder;
use AdyenLib\Models\ValueEnum;
use AdyenLib\Models\Builders\CountriesRestriction1Builder;
use AdyenLib\Models\Type141Enum;
use AdyenLib\Models\OutcomeTypeEnum;

$transactionRuleResponse = TransactionRuleResponseBuilder::init()
    ->transactionRule(
        TransactionRule1Builder::init(
            'description2',
            TransactionRuleEntityKey2Builder::init()
                ->entityReference('entityReference2')
                ->entityType('entityType0')
                ->build(),
            TransactionRuleInterval1Builder::init(
                Type131Enum::MONTHLY
            )
                ->dayOfMonth(178)
                ->dayOfWeek(DayOfWeekEnum::SATURDAY)
                ->duration(
                    Duration1Builder::init()
                        ->unit(UnitEnum::WEEKS)
                        ->value(176)
                        ->build()
                )
                ->timeOfDay('timeOfDay2')
                ->timeZone('timeZone4')
                ->build(),
            'reference2',
            TransactionRuleRestrictions1Builder::init()
                ->activeNetworkTokens(
                    ActiveNetworkTokensRestriction1Builder::init(
                        'operation0'
                    )
                        ->value(202)
                        ->build()
                )
                ->brandVariants(
                    BrandVariantsRestriction1Builder::init(
                        'operation4'
                    )
                        ->value(
                            [
                                'value8',
                                'value9'
                            ]
                        )
                        ->build()
                )
                ->counterpartyBank(
                    CounterpartyBankRestriction1Builder::init(
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
                                    ->build()
                            ]
                        )
                        ->build()
                )
                ->counterpartyTypes(
                    CounterpartyTypesRestriction1Builder::init(
                        'operation8'
                    )
                        ->value(
                            [
                                ValueEnum::BALANCEACCOUNT
                            ]
                        )
                        ->build()
                )
                ->countries(
                    CountriesRestriction1Builder::init(
                        'operation0'
                    )
                        ->value(
                            [
                                'value4'
                            ]
                        )
                        ->build()
                )
                ->build(),
            Type141Enum::MAXUSAGE
        )
            ->aggregationLevel('aggregationLevel4')
            ->endDate('endDate4')
            ->id('id2')
            ->outcomeType(OutcomeTypeEnum::ENFORCESCA)
            ->overridesRule('overridesRule8')
            ->build()
    )
    ->build();
```

