
# Account

## Structure

`Account`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `?string` | Optional | The code of the account. | getAccountCode(): ?string | setAccountCode(?string accountCode): void |
| `bankAccountUUID` | `?string` | Optional | The bankAccountUUID of the bank account held by the account holder to couple the account with. Scheduled payouts in currencies matching the currency of this bank account will be sent to this bank account. Payouts in different currencies will be sent to a matching bank account of the account holder. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `beneficiaryAccount` | `?string` | Optional | The beneficiary of the account. | getBeneficiaryAccount(): ?string | setBeneficiaryAccount(?string beneficiaryAccount): void |
| `beneficiaryMerchantReference` | `?string` | Optional | The reason that a beneficiary has been set up for this account. This may have been supplied during the setup of a beneficiary at the discretion of the executing user. | getBeneficiaryMerchantReference(): ?string | setBeneficiaryMerchantReference(?string beneficiaryMerchantReference): void |
| `description` | `?string` | Optional | A description of the account. | getDescription(): ?string | setDescription(?string description): void |
| `metadata` | `?array<string,string>` | Optional | A set of key and value pairs for general use by the merchant.<br>The keys do not have specific names and may be used for storing miscellaneous data as desired.<br><br>> Note that during an update of metadata, the omission of existing key-value pairs will result in the deletion of those key-value pairs. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `payoutMethodCode` | `?string` | Optional | The payout method code held by the account holder to couple the account with. Scheduled card payouts will be sent using this payout method code. | getPayoutMethodCode(): ?string | setPayoutMethodCode(?string payoutMethodCode): void |
| `payoutSchedule` | [`?PayoutScheduleResponse4`](../../doc/models/payout-schedule-response-4.md) | Optional | The account's payout schedule. | getPayoutSchedule(): ?PayoutScheduleResponse4 | setPayoutSchedule(?PayoutScheduleResponse4 payoutSchedule): void |
| `payoutSpeed` | [`?string(PayoutSpeedEnum)`](../../doc/models/payout-speed-enum.md) | Optional | Speed with which payouts for this account are processed. Permitted values: `STANDARD`, `SAME_DAY`. | getPayoutSpeed(): ?string | setPayoutSpeed(?string payoutSpeed): void |
| `status` | `?string` | Optional | The status of the account. Possible values: `Active`, `Inactive`, `Suspended`, `Closed`. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\AccountBuilder;

$account = AccountBuilder::init()
    ->accountCode('accountCode0')
    ->bankAccountUUID('bankAccountUUID6')
    ->beneficiaryAccount('beneficiaryAccount2')
    ->beneficiaryMerchantReference('beneficiaryMerchantReference2')
    ->description('description0')
    ->build();
```

