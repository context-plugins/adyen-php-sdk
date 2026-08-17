
# Company Balances

## Structure

`CompanyBalances`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantBalancesOverview` | [`?(MerchantBalance[])`](../../doc/models/merchant-balance.md) | Optional | - | getMerchantBalancesOverview(): ?array | setMerchantBalancesOverview(?array merchantBalancesOverview): void |

## Example

```php
use AdyenLib\Models\Builders\CompanyBalancesBuilder;
use AdyenLib\Models\Builders\MerchantBalanceBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$companyBalances = CompanyBalancesBuilder::init()
    ->merchantBalancesOverview(
        [
            MerchantBalanceBuilder::init()
                ->availableFund(
                    Amount17Builder::init(
                        'currency4',
                        152
                    )->build()
                )
                ->deposit(
                    Amount17Builder::init(
                        'currency4',
                        62
                    )->build()
                )
                ->merchantAccount('merchantAccount4')
                ->nextPayout(
                    Amount17Builder::init(
                        'currency4',
                        240
                    )->build()
                )
                ->pendingBalance(
                    Amount17Builder::init(
                        'currency2',
                        254
                    )->build()
                )->build(),
            MerchantBalanceBuilder::init()
                ->availableFund(
                    Amount17Builder::init(
                        'currency4',
                        152
                    )->build()
                )
                ->deposit(
                    Amount17Builder::init(
                        'currency4',
                        62
                    )->build()
                )
                ->merchantAccount('merchantAccount4')
                ->nextPayout(
                    Amount17Builder::init(
                        'currency4',
                        240
                    )->build()
                )
                ->pendingBalance(
                    Amount17Builder::init(
                        'currency2',
                        254
                    )->build()
                )->build()
        ]
    )->build();
```

