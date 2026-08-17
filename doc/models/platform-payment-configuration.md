
# Platform Payment Configuration

## Structure

`PlatformPaymentConfiguration`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `salesDayClosingTime` | `?DateTime` | Optional | Specifies at what time a sales day ends for this account.<br><br>Possible values: Time in **"HH:MM"** format. **HH** ranges from **00** to **07**. **MM** must be **00**.<br><br>Default value: **"00:00"**. | getSalesDayClosingTime(): ?\DateTime | setSalesDayClosingTime(?\DateTime salesDayClosingTime): void |
| `settlementDelayDays` | `?int` | Optional | Specifies after how many business days the funds in a settlement batch are made available in this balance account. Requires Custom Sales Day Payout to be enabled for your balance account. Contact your account manager or implementation manager to enable this.<br><br>Possible values: **1** to **20**, or **null**.<br><br>Default value: **null**. | getSettlementDelayDays(): ?int | setSettlementDelayDays(?int settlementDelayDays): void |

## Example

```php
use AdyenLib\Models\Builders\PlatformPaymentConfigurationBuilder;
use AdyenLib\Utils\DateTimeHelper;

$platformPaymentConfiguration = PlatformPaymentConfigurationBuilder::init()
    ->salesDayClosingTime(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->settlementDelayDays(80)
    ->build();
```

