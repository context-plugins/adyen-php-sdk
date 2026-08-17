
# Perform Verification Request

## Structure

`PerformVerificationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the account holder to verify. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `accountStateType` | [`string(AccountStateTypeEnum)`](../../doc/models/account-state-type-enum.md) | Required | The state required for the account holder.<br><br>> Permitted values: `Processing`, `Payout`. | getAccountStateType(): string | setAccountStateType(string accountStateType): void |
| `tier` | `int` | Required | The tier required for the account holder. | getTier(): int | setTier(int tier): void |

## Example

```php
use AdyenLib\Models\Builders\PerformVerificationRequestBuilder;
use AdyenLib\Models\AccountStateTypeEnum;

$performVerificationRequest = PerformVerificationRequestBuilder::init(
    'accountHolderCode6',
    AccountStateTypeEnum::LIMITEDPAYOUT,
    110
)->build();
```

