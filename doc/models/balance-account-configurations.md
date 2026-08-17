
# Balance Account Configurations

## Structure

`BalanceAccountConfigurations`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountPayoutSchedules` | [`BalanceAccountConfiguration[]`](../../doc/models/balance-account-configuration.md) | Required | Contains a list of the Balance Account payout schedules. | getBalanceAccountPayoutSchedules(): array | setBalanceAccountPayoutSchedules(array balanceAccountPayoutSchedules): void |
| `link` | [`Link2`](../../doc/models/link-2.md) | Required | Contains links to the next and previous page whenever applicable. | getLink(): Link2 | setLink(Link2 link): void |

## Example

```php
use AdyenLib\Models\Builders\BalanceAccountConfigurationsBuilder;
use AdyenLib\Models\Builders\BalanceAccountConfigurationBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\Link2Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;

$balanceAccountConfigurations = BalanceAccountConfigurationsBuilder::init(
    [
        BalanceAccountConfigurationBuilder::init(
            'balanceAccountId0',
            'balancePlatformPayoutScheduleId8',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
            'transferInstrumentId4'
        )
            ->currency('currency8')
            ->description('description2')
            ->enabled(false)
            ->frequency('frequency6')
            ->frequencyValue(138)
            ->build()
    ],
    Link2Builder::init()
        ->first(
            LinksElementBuilder::init()
                ->href('href2')
                ->build()
        )
        ->last(
            LinksElementBuilder::init()
                ->href('href2')
                ->build()
        )
        ->next(
            LinksElementBuilder::init()
                ->href('href4')
                ->build()
        )
        ->previous(
            LinksElementBuilder::init()
                ->href('href0')
                ->build()
        )
        ->self(
            LinksElementBuilder::init()
                ->href('href0')
                ->build()
        )
        ->build()
)->build();
```

