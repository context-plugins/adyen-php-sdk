
# Balance Platform Configuration

## Structure

`BalancePlatformConfiguration`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `automaticApplication` | `?bool` | Optional | Specifies whether this payout schedule is automatically applied to new balance accounts. | getAutomaticApplication(): ?bool | setAutomaticApplication(?bool automaticApplication): void |
| `balancePlatformId` | `string` | Required | The balance platform to which the payout schedule applies. | getBalancePlatformId(): string | setBalancePlatformId(string balancePlatformId): void |
| `countryCode` | `?string` | Optional | The two-letter [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) code of the country to which the payout schedule applies. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `createdAt` | `DateTime` | Required | The date when the payout schedule was created. | getCreatedAt(): \DateTime | setCreatedAt(\DateTime createdAt): void |
| `currency` | `?string` | Optional | The three-character [ISO code](https://docs.adyen.com/development-resources/currency-codes) of the currency used for the payout schedule. | getCurrency(): ?string | setCurrency(?string currency): void |
| `defaultDescription` | `?string` | Optional | The default description for payouts initiated by this payout schedule. | getDefaultDescription(): ?string | setDefaultDescription(?string defaultDescription): void |
| `defaultFrequency` | `?string` | Optional | The default frequency of payouts initiated by this payout schedule. | getDefaultFrequency(): ?string | setDefaultFrequency(?string defaultFrequency): void |
| `defaultFrequencyValue` | `?int` | Optional | The default value for date of the month or day of the week when payouts are initiated. Allowed only if `defaultFrequency` is **monthly** or **weekly**.<br><br>Possible values if `defaultFrequency` is **monthly**: **[1 - 31]**.<br><br>* If your specified date happens on a weekend, the payout is initiated on the next business day.<br>* If your specified date (**29**, **30**, or **31**) does not exist in a month, the payout is initiated  on the last day of that month.<br><br>Possible values if `defaultFrequency` is **weekly**: **[1 - 5]**. | getDefaultFrequencyValue(): ?int | setDefaultFrequencyValue(?int defaultFrequencyValue): void |
| `defaultReference` | `?string` | Optional | Your internal default reference for the payout schedule.When the payout schedule is applied to a balance account, this reference is also used for that payout schedule. | getDefaultReference(): ?string | setDefaultReference(?string defaultReference): void |
| `defaultReferenceForBeneficiary` | `?string` | Optional | The default reference for beneficiary for payouts initiated by this payout schedule. | getDefaultReferenceForBeneficiary(): ?string | setDefaultReferenceForBeneficiary(?string defaultReferenceForBeneficiary): void |
| `enabled` | `?bool` | Optional | Specifies whether the payout schedule is enabled immediately after it is created. | getEnabled(): ?bool | setEnabled(?bool enabled): void |
| `id` | `?string` | Optional | The unique identifier of the payout schedule for your balance platform. | getId(): ?string | setId(?string id): void |
| `maxPayoutAmount` | `?int` | Optional | The maximum amount that can be paid out from balance accounts that use this payout schedule.<br><br>Default value: **0**, which means that there is no maximum limit. | getMaxPayoutAmount(): ?int | setMaxPayoutAmount(?int maxPayoutAmount): void |
| `minPayoutAmount` | `?int` | Optional | The minimum amount that can be paid out from balance accounts that use this payout schedule.<br><br>Default value: **0**. | getMinPayoutAmount(): ?int | setMinPayoutAmount(?int minPayoutAmount): void |
| `payoutScheduleDescription` | `string` | Required | The type of payout schedule. This type indicates how fast funds are paid out to your user.<br><br>Possible values:<br><br>- **Standard**: The funds arrive in your user's transfer instrument two days after the funds are settled.<br>- **Accelerated**: The funds arrive to your user's transfer instrument the day after the funds are settled. | getPayoutScheduleDescription(): string | setPayoutScheduleDescription(string payoutScheduleDescription): void |
| `retainedAmount` | `?int` | Optional | The amount of funds that must remain available in a balance account after an execution of the payout schedule. If the funds in the balance account are less than the retained amount, the execution is not initiated.<br><br>Default value: **0** | getRetainedAmount(): ?int | setRetainedAmount(?int retainedAmount): void |
| `updatedAt` | `?DateTime` | Optional | The date when the payout schedule was updated. | getUpdatedAt(): ?\DateTime | setUpdatedAt(?\DateTime updatedAt): void |
| `userSettlementDelay` | `int` | Required | The default [settlement delay](https://docs.adyen.com/platforms/settle-funds/#settlement-delay) for this payout schedule. | getUserSettlementDelay(): int | setUserSettlementDelay(int userSettlementDelay): void |
| `userSettlementTime` | [`LocalTime2`](../../doc/models/local-time-2.md) | Required | The time when the payout funds are settled in your user's transfer instrument. | getUserSettlementTime(): LocalTime2 | setUserSettlementTime(LocalTime2 userSettlementTime): void |
| `userSettlementTimeZone` | `string` | Required | The timezone of the `userSettlementTime`. | getUserSettlementTimeZone(): string | setUserSettlementTimeZone(string userSettlementTimeZone): void |

## Example

```php
use AdyenLib\Models\Builders\BalancePlatformConfigurationBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\LocalTime2Builder;

$balancePlatformConfiguration = BalancePlatformConfigurationBuilder::init(
    'balancePlatformId2',
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    'payoutScheduleDescription6',
    104,
    LocalTime2Builder::init()
        ->hour(136)
        ->minute(138)
        ->nano(162)
        ->second(200)
        ->build(),
    'userSettlementTimeZone6'
)
    ->automaticApplication(false)
    ->countryCode('countryCode0')
    ->currency('currency4')
    ->defaultDescription('defaultDescription8')
    ->defaultFrequency('defaultFrequency8')
    ->build();
```

