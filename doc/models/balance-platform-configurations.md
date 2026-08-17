
# Balance Platform Configurations

## Structure

`BalancePlatformConfigurations`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balancePlatformPayoutSchedules` | [`BalancePlatformConfiguration[]`](../../doc/models/balance-platform-configuration.md) | Required | Contains a list of the payout schedules configured in your balance platform. | getBalancePlatformPayoutSchedules(): array | setBalancePlatformPayoutSchedules(array balancePlatformPayoutSchedules): void |

## Example

```php
use AdyenLib\Models\Builders\BalancePlatformConfigurationsBuilder;
use AdyenLib\Models\Builders\BalancePlatformConfigurationBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\LocalTime2Builder;

$balancePlatformConfigurations = BalancePlatformConfigurationsBuilder::init(
    [
        BalancePlatformConfigurationBuilder::init(
            'balancePlatformId0',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
            'payoutScheduleDescription6',
            126,
            LocalTime2Builder::init()
                ->hour(136)
                ->minute(138)
                ->nano(162)
                ->second(200)
                ->build(),
            'userSettlementTimeZone4'
        )
            ->automaticApplication(false)
            ->countryCode('countryCode2')
            ->currency('currency2')
            ->defaultDescription('defaultDescription6')
            ->defaultFrequency('defaultFrequency6')
            ->build()
    ]
)->build();
```

