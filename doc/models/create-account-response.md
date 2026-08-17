
# Create Account Response

## Structure

`CreateAccountResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `?string` | Optional | The code of the new account. | getAccountCode(): ?string | setAccountCode(?string accountCode): void |
| `accountHolderCode` | `?string` | Optional | The code of the account holder. | getAccountHolderCode(): ?string | setAccountHolderCode(?string accountHolderCode): void |
| `bankAccountUUID` | `?string` | Optional | The bankAccountUUID of the bank account held by the account holder to couple the account with. Scheduled payouts in currencies matching the currency of this bank account will be sent to this bank account. Payouts in different currencies will be sent to a matching bank account of the account holder. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `description` | `?string` | Optional | The description of the account. | getDescription(): ?string | setDescription(?string description): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | A list of fields that caused the `/createAccount` request to fail. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `metadata` | `?array<string,string>` | Optional | A set of key and value pairs containing metadata. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `payoutMethodCode` | `?string` | Optional | The payout method code held by the account holder to couple the account with. Scheduled card payouts will be sent using this payout method code. | getPayoutMethodCode(): ?string | setPayoutMethodCode(?string payoutMethodCode): void |
| `payoutSchedule` | [`?PayoutScheduleResponse1`](../../doc/models/payout-schedule-response-1.md) | Optional | The details of the payout schedule added to the account. | getPayoutSchedule(): ?PayoutScheduleResponse1 | setPayoutSchedule(?PayoutScheduleResponse1 payoutSchedule): void |
| `payoutSpeed` | [`?string(PayoutSpeedEnum)`](../../doc/models/payout-speed-enum.md) | Optional | Speed with which payouts for this account are processed. Permitted values: `STANDARD`, `SAME_DAY`. | getPayoutSpeed(): ?string | setPayoutSpeed(?string payoutSpeed): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |
| `status` | [`?string(Status42Enum)`](../../doc/models/status-42-enum.md) | Optional | The status of the account.<br><br>> Permitted values: `Active`. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\CreateAccountResponseBuilder;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$createAccountResponse = CreateAccountResponseBuilder::init()
    ->accountCode('accountCode2')
    ->accountHolderCode('accountHolderCode6')
    ->bankAccountUUID('bankAccountUUID4')
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
    ->build();
```

