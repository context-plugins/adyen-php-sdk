
# BR Local Account Identification 1

## Structure

`BRLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `10` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bankCode` | `string` | Required | The 3-digit bank code, with leading zeros.<br><br>**Constraints**: *Minimum Length*: `3`, *Maximum Length*: `3` | getBankCode(): string | setBankCode(string bankCode): void |
| `branchNumber` | `string` | Required | The bank account branch number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `4` | getBranchNumber(): string | setBranchNumber(string branchNumber): void |
| `ispb` | `?string` | Optional | The 8-digit ISPB, with leading zeros.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `8` | getIspb(): ?string | setIspb(?string ispb): void |

## Example

```php
use AdyenLib\Models\Builders\BRLocalAccountIdentification1Builder;

$bRLocalAccountIdentification1 = BRLocalAccountIdentification1Builder::init(
    'accountNumber8',
    'bankCode0',
    'branchNumber0'
)
    ->type('brLocal')
    ->ispb('ispb4')
    ->build();
```

