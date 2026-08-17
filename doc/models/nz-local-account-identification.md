
# NZ Local Account Identification

## Structure

`NZLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 15-16 digit bank account number. The first 2 digits are the bank number, the next 4 digits are the branch number, the next 7 digits are the account number, and the final 2-3 digits are the suffix.<br><br>**Constraints**: *Minimum Length*: `15`, *Maximum Length*: `16` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `type` | `string` | Required, Constant | **nzLocal**<br><br>**Value**: `'nzLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\NZLocalAccountIdentificationBuilder;

$nZLocalAccountIdentification = NZLocalAccountIdentificationBuilder::init(
    'accountNumber4'
)->build();
```

