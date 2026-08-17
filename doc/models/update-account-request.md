
# Update Account Request

## Structure

`UpdateAccountRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `string` | Required | The code of the account to update. | getAccountCode(): string | setAccountCode(string accountCode): void |
| `bankAccountUUID` | `?string` | Optional | The bankAccountUUID of the bank account held by the account holder to couple the account with. Scheduled payouts in currencies matching the currency of this bank account will be sent to this bank account. Payouts in different currencies will be sent to a matching bank account of the account holder. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `description` | `?string` | Optional | A description of the account, maximum 256 characters.You can use alphanumeric characters (A-Z, a-z, 0-9), white spaces, and underscores `_`. | getDescription(): ?string | setDescription(?string description): void |
| `metadata` | `?array<string,string>` | Optional | A set of key and value pairs for general use by the merchant.<br>The keys do not have specific names and may be used for storing miscellaneous data as desired.<br><br>> Note that during an update of metadata, the omission of existing key-value pairs will result in the deletion of those key-value pairs. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `payoutMethodCode` | `?string` | Optional | The payout method code held by the account holder to couple the account with. Scheduled card payouts will be sent using this payout method code. | getPayoutMethodCode(): ?string | setPayoutMethodCode(?string payoutMethodCode): void |
| `payoutSchedule` | [`?UpdatePayoutScheduleRequest2`](../../doc/models/update-payout-schedule-request-2.md) | Optional | The details of the payout schedule to which the account must be updated. | getPayoutSchedule(): ?UpdatePayoutScheduleRequest2 | setPayoutSchedule(?UpdatePayoutScheduleRequest2 payoutSchedule): void |
| `payoutSpeed` | [`?string(PayoutSpeed1Enum)`](../../doc/models/payout-speed-1-enum.md) | Optional | Speed at which payouts for this account are processed.<br><br>Possible values: `STANDARD` (default), `SAME_DAY`. | getPayoutSpeed(): ?string | setPayoutSpeed(?string payoutSpeed): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateAccountRequestBuilder;
use AdyenLib\Models\Builders\UpdatePayoutScheduleRequest2Builder;
use AdyenLib\Models\Schedule1Enum;
use AdyenLib\Models\ActionEnum;

$updateAccountRequest = UpdateAccountRequestBuilder::init(
    'accountCode0'
)
    ->bankAccountUUID('bankAccountUUID6')
    ->description('description0')
    ->metadata(
        [
            'key0' => 'metadata7'
        ]
    )
    ->payoutMethodCode('payoutMethodCode0')
    ->payoutSchedule(
        UpdatePayoutScheduleRequest2Builder::init(
            Schedule1Enum::WEEKLY_ON_TUE_FRI_MIDNIGHT
        )
            ->action(ActionEnum::NOTHING)
            ->reason('reason0')
            ->build()
    )
    ->build();
```

