
# BR Local Account Identification

## Structure

`BRLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `10` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bankCode` | `string` | Required | The 3-digit bank code, with leading zeros.<br><br>**Constraints**: *Minimum Length*: `3`, *Maximum Length*: `3` | getBankCode(): string | setBankCode(string bankCode): void |
| `branchNumber` | `string` | Required | The bank account branch number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `4` | getBranchNumber(): string | setBranchNumber(string branchNumber): void |
| `ispb` | `?string` | Optional | The 8-digit ISPB, with leading zeros.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `8` | getIspb(): ?string | setIspb(?string ispb): void |
| `type` | `string` | Required, Constant | **brLocal**<br><br>**Value**: `'brLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\BRLocalAccountIdentificationBuilder;

$bRLocalAccountIdentification = BRLocalAccountIdentificationBuilder::init(
    'accountNumber0',
    'bankCode2',
    'branchNumber2'
)
    ->ispb('ispb6')
    ->build();
```

