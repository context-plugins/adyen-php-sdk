
# CA Local Account Identification 1

## Structure

`CALocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 5- to 12-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `5`, *Maximum Length*: `12` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `accountType` | [`?string(AccountType2Enum)`](../../doc/models/account-type-2-enum.md) | Optional | The bank account type.<br><br>Possible values: **checking** or **savings**. Defaults to **checking**. | getAccountType(): ?string | setAccountType(?string accountType): void |
| `institutionNumber` | `string` | Required | The 3-digit institution number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `3`, *Maximum Length*: `3` | getInstitutionNumber(): string | setInstitutionNumber(string institutionNumber): void |
| `transitNumber` | `string` | Required | The 5-digit transit number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `5`, *Maximum Length*: `5` | getTransitNumber(): string | setTransitNumber(string transitNumber): void |

## Example

```php
use AdyenLib\Models\Builders\CALocalAccountIdentification1Builder;
use AdyenLib\Models\AccountType2Enum;

$cALocalAccountIdentification1 = CALocalAccountIdentification1Builder::init(
    'accountNumber4',
    'institutionNumber2',
    'transitNumber4'
)
    ->type('caLocal')
    ->accountType(AccountType2Enum::CHECKING)
    ->build();
```

