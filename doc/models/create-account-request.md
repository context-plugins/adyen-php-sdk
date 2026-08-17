
# Create Account Request

## Structure

`CreateAccountRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of Account Holder under which to create the account. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `bankAccountUUID` | `?string` | Optional | The bankAccountUUID of the bank account held by the account holder to couple the account with. Scheduled payouts in currencies matching the currency of this bank account will be sent to this bank account. Payouts in different currencies will be sent to a matching bank account of the account holder. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `description` | `?string` | Optional | A description of the account, maximum 256 characters. You can use alphanumeric characters (A-Z, a-z, 0-9), white spaces, and underscores `_`. | getDescription(): ?string | setDescription(?string description): void |
| `metadata` | `?array<string,string>` | Optional | A set of key and value pairs for general use by the merchant.<br>The keys do not have specific names and may be used for storing miscellaneous data as desired.<br><br>> Note that during an update of metadata, the omission of existing key-value pairs will result in the deletion of those key-value pairs. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `payoutMethodCode` | `?string` | Optional | The payout method code held by the account holder to couple the account with. Scheduled card payouts will be sent using this payout method code. | getPayoutMethodCode(): ?string | setPayoutMethodCode(?string payoutMethodCode): void |
| `payoutSchedule` | [`?string(PayoutScheduleEnum)`](../../doc/models/payout-schedule-enum.md) | Optional | The payout schedule for the account.<br><br>Possible values: `DEFAULT`, `DAILY`, `DAILY_US`, `DAILY_EU`, `DAILY_AU`, `DAILY_SG`, `WEEKLY`, `WEEKLY_ON_TUE_FRI_MIDNIGHT`, `BIWEEKLY_ON_1ST_AND_15TH_AT_MIDNIGHT`, `MONTHLY`, `HOLD`.<br><br>> `HOLD` prevents scheduled payouts, but you can still initiate payouts manually. | getPayoutSchedule(): ?string | setPayoutSchedule(?string payoutSchedule): void |
| `payoutScheduleReason` | `?string` | Optional | The reason for the payout schedule choice.<br><br>> This field is required when the `payoutSchedule` parameter is set to `HOLD`. | getPayoutScheduleReason(): ?string | setPayoutScheduleReason(?string payoutScheduleReason): void |
| `payoutSpeed` | [`?string(PayoutSpeed1Enum)`](../../doc/models/payout-speed-1-enum.md) | Optional | Speed at which payouts for this account are processed.<br><br>Possible values: `STANDARD` (default), `SAME_DAY`.<br><br>**Default**: `PayoutSpeed1Enum::STANDARD` | getPayoutSpeed(): ?string | setPayoutSpeed(?string payoutSpeed): void |

## Example

```php
use AdyenLib\Models\Builders\CreateAccountRequestBuilder;
use AdyenLib\Models\PayoutScheduleEnum;
use AdyenLib\Models\PayoutSpeed1Enum;

$createAccountRequest = CreateAccountRequestBuilder::init(
    'accountHolderCode8'
)
    ->bankAccountUUID('bankAccountUUID2')
    ->description('description4')
    ->metadata(
        [
            'key0' => 'metadata7',
            'key1' => 'metadata8'
        ]
    )
    ->payoutMethodCode('payoutMethodCode4')
    ->payoutSchedule(PayoutScheduleEnum::BIWEEKLY_ON_1ST_AND_15TH_AT_MIDNIGHT)
    ->payoutSpeed(PayoutSpeed1Enum::STANDARD)
    ->build();
```

