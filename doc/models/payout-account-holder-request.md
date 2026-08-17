
# Payout Account Holder Request

## Structure

`PayoutAccountHolderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `string` | Required | The code of the account from which the payout is to be made. | getAccountCode(): string | setAccountCode(string accountCode): void |
| `accountHolderCode` | `string` | Required | The code of the Account Holder who owns the account from which the payout is to be made.<br>The Account Holder is the party to which the payout will be made. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `amount` | [`?Amount`](../../doc/models/amount.md) | Optional | An object containing the currency and value of the payout.<br>If the account has multiple currencies, specify the currency to be used.<br>If the `bankAccountUUID` is provided in the request, the currency supported by the bank is used.<br>If the `payoutMethodCode` is provided in the request, the specified payout method is selected. | getAmount(): ?Amount | setAmount(?Amount amount): void |
| `bankAccountUUID` | `?string` | Optional | The unique ID of the Bank Account held by the Account Holder to which the payout is to be made.<br>If left blank, a bank account is automatically selected. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `description` | `?string` | Optional | A description of the payout. Maximum 200 characters.<br>Allowed: **abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789/?:().,'+ ";**<br><br>**Constraints**: *Maximum Length*: `200` | getDescription(): ?string | setDescription(?string description): void |
| `merchantReference` | `?string` | Optional | A value that can be supplied at the discretion of the executing user in order to link multiple transactions to one another. | getMerchantReference(): ?string | setMerchantReference(?string merchantReference): void |
| `payoutMethodCode` | `?string` | Optional | The unique ID of the payout method held by the Account Holder to which the payout is to be made.<br>If left blank, a payout instrument is automatically selected. | getPayoutMethodCode(): ?string | setPayoutMethodCode(?string payoutMethodCode): void |
| `payoutSpeed` | [`?string(PayoutSpeedEnum)`](../../doc/models/payout-speed-enum.md) | Optional | Speed with which payouts for this account are processed. Permitted values: `STANDARD`, `SAME_DAY`.<br><br>**Default**: `PayoutSpeedEnum::STANDARD` | getPayoutSpeed(): ?string | setPayoutSpeed(?string payoutSpeed): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutAccountHolderRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\PayoutSpeedEnum;

$payoutAccountHolderRequest = PayoutAccountHolderRequestBuilder::init(
    'accountCode0',
    'accountHolderCode4'
)
    ->amount(
        AmountBuilder::init(
            'currency2',
            110
        )->build()
    )
    ->bankAccountUUID('bankAccountUUID6')
    ->description('description0')
    ->merchantReference('merchantReference6')
    ->payoutMethodCode('payoutMethodCode0')
    ->payoutSpeed(PayoutSpeedEnum::STANDARD)
    ->build();
```

