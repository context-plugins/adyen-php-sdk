
# Transaction Rule Restrictions 1

Contains one or more objects that define the [rule conditions](https://docs.adyen.com/issuing/transaction-rules#conditions). Each object must have a value and an operation which determines how the values must be evaluated.

For example, a `countries` object can have a list of country codes **["US", "CA"]** in the `value` field and **anyMatch** in the `operation` field.

## Structure

`TransactionRuleRestrictions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `activeNetworkTokens` | [`?ActiveNetworkTokensRestriction1`](../../doc/models/active-network-tokens-restriction-1.md) | Optional | The total number of tokens that a card can have across different kinds of digital wallets on the user's phones, watches, or other wearables.<br><br>Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**. | getActiveNetworkTokens(): ?ActiveNetworkTokensRestriction1 | setActiveNetworkTokens(?ActiveNetworkTokensRestriction1 activeNetworkTokens): void |
| `brandVariants` | [`?BrandVariantsRestriction1`](../../doc/models/brand-variants-restriction-1.md) | Optional | List of card brand variants and the operation.<br><br>Supported operations: **anyMatch**, **noneMatch**. | getBrandVariants(): ?BrandVariantsRestriction1 | setBrandVariants(?BrandVariantsRestriction1 brandVariants): void |
| `counterpartyBank` | [`?CounterpartyBankRestriction1`](../../doc/models/counterparty-bank-restriction-1.md) | Optional | Contains a list of counterparty financial institutions and how they must be evaluated.<br><br>Supported operations: **anyMatch**, **noneMatch**. | getCounterpartyBank(): ?CounterpartyBankRestriction1 | setCounterpartyBank(?CounterpartyBankRestriction1 counterpartyBank): void |
| `counterpartyTypes` | [`?CounterpartyTypesRestriction1`](../../doc/models/counterparty-types-restriction-1.md) | Optional | Contains a list of counterparty types and how they must be evaluated.<br><br>Supported operations: **anyMatch**, **noneMatch**.<br><br>Supported value inputs:<br><br>- **balanceAccount**<br>- **bankAccount**<br>- **card**<br>- **transferInstrument** | getCounterpartyTypes(): ?CounterpartyTypesRestriction1 | setCounterpartyTypes(?CounterpartyTypesRestriction1 counterpartyTypes): void |
| `countries` | [`?CountriesRestriction1`](../../doc/models/countries-restriction-1.md) | Optional | List of countries and the operation.<br><br>Supported operations: **anyMatch**, **noneMatch**. | getCountries(): ?CountriesRestriction1 | setCountries(?CountriesRestriction1 countries): void |
| `dayOfWeek` | [`?DayOfWeekRestriction1`](../../doc/models/day-of-week-restriction-1.md) | Optional | List of week days and the operation. Supported operations: **anyMatch**, **noneMatch**. | getDayOfWeek(): ?DayOfWeekRestriction1 | setDayOfWeek(?DayOfWeekRestriction1 dayOfWeek): void |
| `differentCurrencies` | [`?DifferentCurrenciesRestriction1`](../../doc/models/different-currencies-restriction-1.md) | Optional | Compares the currency of the payment against the currency of the payment instrument, and specifies the operation.<br><br>Supported operations: **equals**, **notEquals**. | getDifferentCurrencies(): ?DifferentCurrenciesRestriction1 | setDifferentCurrencies(?DifferentCurrenciesRestriction1 differentCurrencies): void |
| `entryModes` | [`?EntryModesRestriction1`](../../doc/models/entry-modes-restriction-1.md) | Optional | List of point-of-sale entry modes and the operation..<br><br>Supported operations: **anyMatch**, **noneMatch**. | getEntryModes(): ?EntryModesRestriction1 | setEntryModes(?EntryModesRestriction1 entryModes): void |
| `internationalTransaction` | [`?InternationalTransactionRestriction1`](../../doc/models/international-transaction-restriction-1.md) | Optional | Indicates whether transaction is an international transaction and specifies the operation.<br><br>Supported operations: **equals**, **notEquals**. | getInternationalTransaction(): ?InternationalTransactionRestriction1 | setInternationalTransaction(?InternationalTransactionRestriction1 internationalTransaction): void |
| `matchingTransactions` | [`?MatchingTransactionsRestriction1`](../../doc/models/matching-transactions-restriction-1.md) | Optional | The number of transactions and the operation.<br><br>Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**. | getMatchingTransactions(): ?MatchingTransactionsRestriction1 | setMatchingTransactions(?MatchingTransactionsRestriction1 matchingTransactions): void |
| `matchingValues` | [`?MatchingValuesRestriction1`](../../doc/models/matching-values-restriction-1.md) | Optional | Checks if a user has recently made multiple transfers with the specified values.<br><br>To use this restriction, you must:<br><br>- Set the rule `type` to **velocity**.<br><br>- Specify a time `interval`.<br><br>- Specify a number of `matchingTransactions`.<br><br>Supported operation: **allMatch**.<br><br>Supported value inputs:<br><br>- **merchantId** and **acquirerId**<br>- **amount** and **currency**<br>- **merchantName**. | getMatchingValues(): ?MatchingValuesRestriction1 | setMatchingValues(?MatchingValuesRestriction1 matchingValues): void |
| `mccs` | [`?MccsRestriction1`](../../doc/models/mccs-restriction-1.md) | Optional | List of merchant category codes (MCCs) and the operation.<br><br>Supported operations: **anyMatch**, **noneMatch**. | getMccs(): ?MccsRestriction1 | setMccs(?MccsRestriction1 mccs): void |
| `merchantNames` | [`?MerchantNamesRestriction1`](../../doc/models/merchant-names-restriction-1.md) | Optional | List of names that will be compared to the merchant name according to the matching type.<br><br>Supported operations: **anyMatch**, **noneMatch**. | getMerchantNames(): ?MerchantNamesRestriction1 | setMerchantNames(?MerchantNamesRestriction1 merchantNames): void |
| `merchants` | [`?MerchantsRestriction1`](../../doc/models/merchants-restriction-1.md) | Optional | List of merchant ID and acquirer ID pairs, and the operation.<br><br>Supported operations: **anyMatch**, **noneMatch**. | getMerchants(): ?MerchantsRestriction1 | setMerchants(?MerchantsRestriction1 merchants): void |
| `processingTypes` | [`?ProcessingTypesRestriction1`](../../doc/models/processing-types-restriction-1.md) | Optional | List of processing types and the operation.<br><br>Supported operations: **anyMatch**, **noneMatch**. | getProcessingTypes(): ?ProcessingTypesRestriction1 | setProcessingTypes(?ProcessingTypesRestriction1 processingTypes): void |
| `riskScores` | [`?RiskScoresRestriction1`](../../doc/models/risk-scores-restriction-1.md) | Optional | Risk scores provided by specific sources. The same operation applies to all scores.<br><br>Current sources available: **visa**, **mastercard**<br><br>Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**. | getRiskScores(): ?RiskScoresRestriction1 | setRiskScores(?RiskScoresRestriction1 riskScores): void |
| `sameAmountRestriction` | [`?SameAmountRestriction1`](../../doc/models/same-amount-restriction-1.md) | Optional | Checks if a user has recently sent the same amount of funds in multiple transfers.<br><br>To use this restriction, you must:<br><br>- Set the rule `type` to **velocity**.<br><br>- Specify a time `interval`.<br><br>- Specify a number of `matchingTransactions`.<br><br>Supported operation: **equals**. | getSameAmountRestriction(): ?SameAmountRestriction1 | setSameAmountRestriction(?SameAmountRestriction1 sameAmountRestriction): void |
| `sameCounterpartyRestriction` | [`?SameCounterpartyRestriction1`](../../doc/models/same-counterparty-restriction-1.md) | Optional | Checks if a user has recently made multiple transfers to the same counterparty.<br><br>To use this restriction, you must:<br><br>- Set the rule `type` to **velocity**.<br><br>- Specify a time `interval`.<br><br>- Specify a number of `matchingTransactions`.<br><br>Supported operations: **equals**. | getSameCounterpartyRestriction(): ?SameCounterpartyRestriction1 | setSameCounterpartyRestriction(?SameCounterpartyRestriction1 sameCounterpartyRestriction): void |
| `sourceAccountTypes` | [`?SourceAccountTypesRestriction1`](../../doc/models/source-account-types-restriction-1.md) | Optional | Contains a list of source account types and how they must be evaluated.<br><br>Supported operations: **anyMatch**, **noneMatch**.<br><br>Supported value inputs:<br><br>- **balanceAccount**<br>- **businessAccount**. | getSourceAccountTypes(): ?SourceAccountTypesRestriction1 | setSourceAccountTypes(?SourceAccountTypesRestriction1 sourceAccountTypes): void |
| `timeOfDay` | [`?TimeOfDayRestriction1`](../../doc/models/time-of-day-restriction-1.md) | Optional | A start and end time in a time-only ISO-8601 extended offset format. Supported operations: **equals**, **notEquals**. | getTimeOfDay(): ?TimeOfDayRestriction1 | setTimeOfDay(?TimeOfDayRestriction1 timeOfDay): void |
| `tokenRequestors` | [`?TokenRequestorsRestriction1`](../../doc/models/token-requestors-restriction-1.md) | Optional | List of token requestor IDs and the operation.<br><br>Supported operations: **anyMatch**, **noneMatch**. | getTokenRequestors(): ?TokenRequestorsRestriction1 | setTokenRequestors(?TokenRequestorsRestriction1 tokenRequestors): void |
| `totalAmount` | [`?TotalAmountRestriction1`](../../doc/models/total-amount-restriction-1.md) | Optional | The total amount and the operation.<br><br>Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**. | getTotalAmount(): ?TotalAmountRestriction1 | setTotalAmount(?TotalAmountRestriction1 totalAmount): void |
| `walletProviderAccountScore` | [`?WalletProviderAccountScoreRestriction2`](../../doc/models/wallet-provider-account-score-restriction-2.md) | Optional | Checks the wallet account score.<br><br>Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**. | getWalletProviderAccountScore(): ?WalletProviderAccountScoreRestriction2 | setWalletProviderAccountScore(?WalletProviderAccountScoreRestriction2 walletProviderAccountScore): void |
| `walletProviderDeviceScore` | [`?WalletProviderDeviceScore2`](../../doc/models/wallet-provider-device-score-2.md) | Optional | Wallet Provider Device Score and the operation.<br><br>Supported operations: **equals**, **notEquals**, **greaterThanOrEqualTo**, **greaterThan**, **lessThanOrEqualTo**, **lessThan**. | getWalletProviderDeviceScore(): ?WalletProviderDeviceScore2 | setWalletProviderDeviceScore(?WalletProviderDeviceScore2 walletProviderDeviceScore): void |
| `walletProviderDeviceType` | [`?WalletProviderDeviceType2`](../../doc/models/wallet-provider-device-type-2.md) | Optional | Wallet Provider Device Type and the operation.<br><br>Supported operations: **anyMatch**, **noneMatch**.<br><br>Supported value inputs:<br><br>- **MOBILE_PHONE**<br><br>- **TABLET_OR_EREADER**<br><br>- **WATCH_OR_WRISTBAND**<br><br>- **WEARABLE**<br><br>- **CARD**<br><br>- **PC**<br><br>- **OTHER**<br><br>- **UNKNOWN** | getWalletProviderDeviceType(): ?WalletProviderDeviceType2 | setWalletProviderDeviceType(?WalletProviderDeviceType2 walletProviderDeviceType): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionRuleRestrictions1Builder;
use AdyenLib\Models\Builders\ActiveNetworkTokensRestriction1Builder;
use AdyenLib\Models\Builders\BrandVariantsRestriction1Builder;
use AdyenLib\Models\Builders\CounterpartyBankRestriction1Builder;
use AdyenLib\Models\Builders\BankIdentificationBuilder;
use AdyenLib\Models\IdentificationTypeEnum;
use AdyenLib\Models\Builders\CounterpartyTypesRestriction1Builder;
use AdyenLib\Models\ValueEnum;
use AdyenLib\Models\Builders\CountriesRestriction1Builder;

$transactionRuleRestrictions1 = TransactionRuleRestrictions1Builder::init()
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
    ->build();
```

