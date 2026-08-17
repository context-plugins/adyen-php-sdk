
# Split Configuration

## Structure

`SplitConfiguration`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `string` | Required | Your description for the split configuration.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): string | setDescription(string description): void |
| `rules` | [`SplitConfigurationRule[]`](../../doc/models/split-configuration-rule.md) | Required | Array of rules that define the split configuration behavior. | getRules(): array | setRules(array rules): void |
| `splitConfigurationId` | `?string` | Optional, Read-only | Unique identifier of the split configuration. | getSplitConfigurationId(): ?string | setSplitConfigurationId(?string splitConfigurationId): void |

## Example

```php
use AdyenLib\Models\Builders\SplitConfigurationBuilder;
use AdyenLib\Models\Builders\SplitConfigurationRuleBuilder;
use AdyenLib\Models\FundingSource1Enum;
use AdyenLib\Models\ShopperInteraction11Enum;
use AdyenLib\Models\Builders\SplitConfigurationLogic2Builder;
use AdyenLib\Models\Builders\Commission1Builder;
use AdyenLib\Models\AcquiringFeesEnum;
use AdyenLib\Models\Builders\AdditionalCommission1Builder;
use AdyenLib\Models\AdyenCommissionEnum;
use AdyenLib\Models\AdyenFeesEnum;
use AdyenLib\Models\AdyenMarkupEnum;
use AdyenLib\Models\CardRegionEnum;

$splitConfiguration = SplitConfigurationBuilder::init(
    'description0',
    [
        SplitConfigurationRuleBuilder::init(
            'currency2',
            FundingSource1Enum::PREPAID,
            'paymentMethod4',
            ShopperInteraction11Enum::ANY,
            SplitConfigurationLogic2Builder::init(
                Commission1Builder::init()
                    ->fixedAmount(112)
                    ->variablePercentage(52)
                    ->build()
            )
                ->acquiringFees(AcquiringFeesEnum::DEDUCTFROMLIABLEACCOUNT)
                ->additionalCommission(
                    AdditionalCommission1Builder::init()
                        ->balanceAccountId('balanceAccountId0')
                        ->fixedAmount(100)
                        ->variablePercentage(64)
                        ->build()
                )
                ->adyenCommission(AdyenCommissionEnum::DEDUCTFROMLIABLEACCOUNT)
                ->adyenFees(AdyenFeesEnum::DEDUCTFROMLIABLEACCOUNT)
                ->adyenMarkup(AdyenMarkupEnum::DEDUCTFROMLIABLEACCOUNT)
                ->build()
        )
            ->cardRegion(CardRegionEnum::INTERNATIONAL)
            ->build()
    ]
)->build();
```

