
# Split Configuration List

## Structure

`SplitConfigurationList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(SplitConfiguration[])`](../../doc/models/split-configuration.md) | Optional | List of split configurations applied to the stores under the merchant account. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\SplitConfigurationListBuilder;
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

$splitConfigurationList = SplitConfigurationListBuilder::init()
    ->data(
        [
            SplitConfigurationBuilder::init(
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
                        ->build(),
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
            )->build()
        ]
    )->build();
```

