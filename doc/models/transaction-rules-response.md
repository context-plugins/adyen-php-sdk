
# Transaction Rules Response

## Structure

`TransactionRulesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionRules` | [`?(TransactionRule[])`](../../doc/models/transaction-rule.md) | Optional | List of transaction rules. | getTransactionRules(): ?array | setTransactionRules(?array transactionRules): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRulesResponseBuilder;
use AdyenLib\Models\Builders\TransactionRuleBuilder;
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

$transactionRulesResponse = TransactionRulesResponseBuilder::init()
    ->transactionRules(
        [
            TransactionRuleBuilder::init(
                'description8',
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
                'reference4',
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
                ->aggregationLevel('aggregationLevel0')
                ->endDate('endDate0')
                ->id('id8')
                ->outcomeType(OutcomeTypeEnum::SCOREBASED)
                ->overridesRule('overridesRule4')
                ->build(),
            TransactionRuleBuilder::init(
                'description8',
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
                'reference4',
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
                ->aggregationLevel('aggregationLevel0')
                ->endDate('endDate0')
                ->id('id8')
                ->outcomeType(OutcomeTypeEnum::SCOREBASED)
                ->overridesRule('overridesRule4')
                ->build()
        ]
    )
    ->build();
```

