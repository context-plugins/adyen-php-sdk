
# Update Account Response

## Structure

`UpdateAccountResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `string` | Required | The code of the account. | getAccountCode(): string | setAccountCode(string accountCode): void |
| `bankAccountUUID` | `?string` | Optional | The bankAccountUUID of the bank account held by the account holder to couple the account with. Scheduled payouts in currencies matching the currency of this bank account will be sent to this bank account. Payouts in different currencies will be sent to a matching bank account of the account holder. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `description` | `?string` | Optional | The description of the account. | getDescription(): ?string | setDescription(?string description): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | A list of fields that caused the `/updateAccount` request to fail. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `metadata` | `?array<string,string>` | Optional | A set of key and value pairs containing metadata. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `payoutMethodCode` | `?string` | Optional | The payout method code held by the account holder to couple the account with. Scheduled card payouts will be sent using this payout method code. | getPayoutMethodCode(): ?string | setPayoutMethodCode(?string payoutMethodCode): void |
| `payoutSchedule` | [`?PayoutScheduleResponse3`](../../doc/models/payout-schedule-response-3.md) | Optional | The details of the payout schedule to which the account is updated. | getPayoutSchedule(): ?PayoutScheduleResponse3 | setPayoutSchedule(?PayoutScheduleResponse3 payoutSchedule): void |
| `payoutSpeed` | [`?string(PayoutSpeed4Enum)`](../../doc/models/payout-speed-4-enum.md) | Optional | Speed at which payouts for this account are processed.<br><br>Possible values: `STANDARD`, `SAME_DAY`. | getPayoutSpeed(): ?string | setPayoutSpeed(?string payoutSpeed): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateAccountResponseBuilder;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$updateAccountResponse = UpdateAccountResponseBuilder::init(
    'accountCode2'
)
    ->bankAccountUUID('bankAccountUUID8')
    ->description('description2')
    ->invalidFields(
        [
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build(),
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build()
        ]
    )
    ->metadata(
        [
            'key0' => 'metadata9',
            'key1' => 'metadata8',
            'key2' => 'metadata7'
        ]
    )
    ->payoutMethodCode('payoutMethodCode2')
    ->build();
```

