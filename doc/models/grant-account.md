
# Grant Account

## Structure

`GrantAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balances` | [`?(CapitalBalance[])`](../../doc/models/capital-balance.md) | Optional | Contains the sum of the balances of all grants tracked by this grant account. The balances are separated by currency. | getBalances(): ?array | setBalances(?array balances): void |
| `fundingBalanceAccountId` | `?string` | Optional | The unique identifier of the balance account used to fund the grant. | getFundingBalanceAccountId(): ?string | setFundingBalanceAccountId(?string fundingBalanceAccountId): void |
| `id` | `?string` | Optional | The unique identifier of the grant account. | getId(): ?string | setId(?string id): void |
| `limits` | [`?(GrantLimit1[])`](../../doc/models/grant-limit-1.md) | Optional | Contains the maximum amount of funds that you can disburse for grants. | getLimits(): ?array | setLimits(?array limits): void |

## Example

```php
use AdyenLib\Models\Builders\GrantAccountBuilder;
use AdyenLib\Models\Builders\CapitalBalanceBuilder;
use AdyenLib\Models\Builders\GrantLimit1Builder;
use AdyenLib\Models\Builders\Amount17Builder;

$grantAccount = GrantAccountBuilder::init()
    ->balances(
        [
            CapitalBalanceBuilder::init(
                'currency0',
                72,
                110,
                150
            )->build()
        ]
    )
    ->fundingBalanceAccountId('fundingBalanceAccountId0')
    ->id('id2')
    ->limits(
        [
            GrantLimit1Builder::init()
                ->amount(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )->build()
        ]
    )->build();
```

