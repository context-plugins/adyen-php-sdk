
# Capital Grant Account

## Structure

`CapitalGrantAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balances` | [`?(CapitalBalance[])`](../../doc/models/capital-balance.md) | Optional | The balances of the grant account. | getBalances(): ?array | setBalances(?array balances): void |
| `fundingBalanceAccountId` | `?string` | Optional | The unique identifier of the balance account used to fund the grant. | getFundingBalanceAccountId(): ?string | setFundingBalanceAccountId(?string fundingBalanceAccountId): void |
| `id` | `?string` | Optional | The identifier of the grant account. | getId(): ?string | setId(?string id): void |
| `limits` | [`?(GrantLimit[])`](../../doc/models/grant-limit.md) | Optional | The limits of the grant account. | getLimits(): ?array | setLimits(?array limits): void |

## Example

```php
use AdyenLib\Models\Builders\CapitalGrantAccountBuilder;
use AdyenLib\Models\Builders\CapitalBalanceBuilder;
use AdyenLib\Models\Builders\GrantLimitBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$capitalGrantAccount = CapitalGrantAccountBuilder::init()
    ->balances(
        [
            CapitalBalanceBuilder::init(
                'currency0',
                72,
                110,
                150
            )->build(),
            CapitalBalanceBuilder::init(
                'currency0',
                72,
                110,
                150
            )->build(),
            CapitalBalanceBuilder::init(
                'currency0',
                72,
                110,
                150
            )->build()
        ]
    )
    ->fundingBalanceAccountId('fundingBalanceAccountId6')
    ->id('id6')
    ->limits(
        [
            GrantLimitBuilder::init()
                ->amount(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )->build(),
            GrantLimitBuilder::init()
                ->amount(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )->build(),
            GrantLimitBuilder::init()
                ->amount(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )->build()
        ]
    )->build();
```

