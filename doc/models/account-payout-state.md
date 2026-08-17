
# Account Payout State

## Structure

`AccountPayoutState`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowPayout` | `?bool` | Optional | Indicates whether payouts are allowed. This field is the overarching payout status, and is the aggregate of multiple conditions (e.g., KYC status, disabled flag, etc). If this field is false, no payouts will be permitted for any of the account holder's accounts. If this field is true, payouts will be permitted for any of the account holder's accounts. | getAllowPayout(): ?bool | setAllowPayout(?bool allowPayout): void |
| `disableReason` | `?string` | Optional | The reason why payouts (to all of the account holder's accounts) have been disabled (by the platform). If the `disabled` field is true, this field can be used to explain why. | getDisableReason(): ?string | setDisableReason(?string disableReason): void |
| `disabled` | `?bool` | Optional | Indicates whether payouts have been disabled (by the platform) for all of the account holder's accounts. A platform may enable and disable this field at their discretion. If this field is true, `allowPayout` will be false and no payouts will be permitted for any of the account holder's accounts. If this field is false, `allowPayout` may or may not be enabled, depending on other factors. | getDisabled(): ?bool | setDisabled(?bool disabled): void |
| `notAllowedReason` | `?string` | Optional | The reason why payouts (to all of the account holder's accounts) have been disabled (by Adyen). If payouts have been disabled by Adyen, this field will explain why. If this field is blank, payouts have not been disabled by Adyen. | getNotAllowedReason(): ?string | setNotAllowedReason(?string notAllowedReason): void |
| `payoutLimit` | [`?Amount`](../../doc/models/amount.md) | Optional | The maximum amount that payouts are limited to. Only applies if payouts are allowed but limited. | getPayoutLimit(): ?Amount | setPayoutLimit(?Amount payoutLimit): void |
| `tierNumber` | `?int` | Optional | The payout tier that the account holder occupies. | getTierNumber(): ?int | setTierNumber(?int tierNumber): void |

## Example

```php
use AdyenLib\Models\Builders\AccountPayoutStateBuilder;
use AdyenLib\Models\Builders\AmountBuilder;

$accountPayoutState = AccountPayoutStateBuilder::init()
    ->allowPayout(false)
    ->disableReason('disableReason8')
    ->disabled(false)
    ->notAllowedReason('notAllowedReason0')
    ->payoutLimit(
        AmountBuilder::init(
            'currency8',
            88
        )->build()
    )->build();
```

