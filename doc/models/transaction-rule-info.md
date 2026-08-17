
# Transaction Rule Info

## Structure

`TransactionRuleInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `aggregationLevel` | `?string` | Optional | The level at which data must be accumulated, used in rules with `type` **velocity** or **maxUsage**. The level must be the [same or lower in hierarchy](https://docs.adyen.com/issuing/transaction-rules#accumulate-data) than the `entityKey`.<br><br>If not provided, by default, the rule will accumulate data at the **paymentInstrument** level.<br><br>Possible values: **paymentInstrument**, **paymentInstrumentGroup**, **balanceAccount**, **accountHolder**, **balancePlatform**. | getAggregationLevel(): ?string | setAggregationLevel(?string aggregationLevel): void |
| `description` | `string` | Required | Your description for the transaction rule.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): string | setDescription(string description): void |
| `endDate` | `?string` | Optional | The date when the rule will stop being evaluated, in ISO 8601 extended offset date-time format. For example, **2025-03-19T10:15:30+01:00**.<br><br>If not provided, the rule will be evaluated until the rule status is set to **inactive**. | getEndDate(): ?string | setEndDate(?string endDate): void |
| `entityKey` | [`TransactionRuleEntityKey2`](../../doc/models/transaction-rule-entity-key-2.md) | Required | The type and unique identifier of the resource to which the rule applies. | getEntityKey(): TransactionRuleEntityKey2 | setEntityKey(TransactionRuleEntityKey2 entityKey): void |
| `interval` | [`TransactionRuleInterval1`](../../doc/models/transaction-rule-interval-1.md) | Required | The [time interval](https://docs.adyen.com/issuing/transaction-rules#time-intervals) when the rule conditions apply. | getInterval(): TransactionRuleInterval1 | setInterval(TransactionRuleInterval1 interval): void |
| `outcomeType` | [`?string(OutcomeTypeEnum)`](../../doc/models/outcome-type-enum.md) | Optional | The [outcome](https://docs.adyen.com/issuing/transaction-rules#outcome) that will be applied when a transaction meets the conditions of the rule.<br><br>Possible values:<br><br>* **hardBlock** (default): the transaction is declined.<br><br>* **scoreBased**: the transaction is assigned the `score` you specified. Adyen calculates the total score and if it exceeds 100, the transaction is declined. This value is not allowed when `requestType` is **bankTransfer**.<br><br>* **enforceSCA**: your user is prompted to verify their identity using [3D Secure authentication](https://docs.adyen.com/issuing/3d-secure/). If the authentication fails or times out, the transaction is declined. This value is only allowed when `requestType` is **authentication**. | getOutcomeType(): ?string | setOutcomeType(?string outcomeType): void |
| `overridesRule` | `?string` | Optional | The `id` of the transaction rule you want to override or skip for the specified `entityKey`. | getOverridesRule(): ?string | setOverridesRule(?string overridesRule): void |
| `purpose` | [`?string(PurposeEnum)`](../../doc/models/purpose-enum.md) | Optional | Specifies the reason for creating the rule.<br><br>Possible values:<br><br>* **fraud**: the rule is created to regulate fraudulent activity.<br>* **policy**: the rule is created to ensure that the transaction adheres to your business' policies. For example, if your business has policies about the Merchant Category Codes (MCCs) allowed on a transaction, you can create a rule to block transactions that have specific MCCs. | getPurpose(): ?string | setPurpose(?string purpose): void |
| `reference` | `string` | Required | Your reference for the transaction rule.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): string | setReference(string reference): void |
| `requestType` | [`?string(RequestTypeEnum)`](../../doc/models/request-type-enum.md) | Optional | Indicates the type of request to which the rule applies. If not provided, by default, this is set to **authorization**.<br><br>Possible values: **authorization**, **authentication**, **tokenization**, **bankTransfer**. | getRequestType(): ?string | setRequestType(?string requestType): void |
| `ruleRestrictions` | [`TransactionRuleRestrictions1`](../../doc/models/transaction-rule-restrictions-1.md) | Required | Contains one or more objects that define the [rule conditions](https://docs.adyen.com/issuing/transaction-rules#conditions). Each object must have a value and an operation which determines how the values must be evaluated.<br><br>For example, a `countries` object can have a list of country codes **["US", "CA"]** in the `value` field and **anyMatch** in the `operation` field. | getRuleRestrictions(): TransactionRuleRestrictions1 | setRuleRestrictions(TransactionRuleRestrictions1 ruleRestrictions): void |
| `score` | `?int` | Optional | A positive or negative score applied to the transaction if it meets the conditions of the rule. Required when `outcomeType` is **scoreBased**.  The value must be between **-100** and **100**. | getScore(): ?int | setScore(?int score): void |
| `startDate` | `?string` | Optional | The date when the rule will start to be evaluated, in ISO 8601 extended offset date-time format. For example, **2025-03-19T10:15:30+01:00**.<br><br>If not provided when creating a transaction rule, the `startDate` is set to the date when the rule status is set to **active**. | getStartDate(): ?string | setStartDate(?string startDate): void |
| `status` | [`?string(Status6Enum)`](../../doc/models/status-6-enum.md) | Optional | The status of the transaction rule. If you provide a `startDate` in the request, the rule is automatically created<br>with an **active** status.<br><br>Possible values: **active**, **inactive**. | getStatus(): ?string | setStatus(?string status): void |
| `type` | [`string(Type141Enum)`](../../doc/models/type-141-enum.md) | Required | The [type of rule](https://docs.adyen.com/issuing/transaction-rules#rule-types), which defines if a rule blocks transactions based on individual characteristics or accumulates data.<br><br>Possible values:<br><br>* **blockList**: decline a transaction when the conditions are met.<br>* **maxUsage**: add the amount or number of transactions for the lifetime of a payment instrument, and then decline a transaction when the specified limits are met.<br>* **velocity**: add the amount or number of transactions based on a specified time interval, and then decline a transaction when the specified limits are met.<br>* **bypass**: bypass or skip a rule for the specified `entityKey`. Transactions processed to that entity are no longer evaluated by the bypassed rule.  You must provide the `id` of the rule to bypass in `overridesRule` and leave the `ruleRestrictions` object empty. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRuleInfoBuilder;
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
use AdyenLib\Models\PurposeEnum;

$transactionRuleInfo = TransactionRuleInfoBuilder::init(
    'description6',
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
    'reference0',
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
    Type141Enum::BLOCKLIST
)
    ->aggregationLevel('aggregationLevel6')
    ->endDate('endDate6')
    ->outcomeType(OutcomeTypeEnum::SCOREBASED)
    ->overridesRule('overridesRule0')
    ->purpose(PurposeEnum::COMPLIANCE)
    ->build();
```

