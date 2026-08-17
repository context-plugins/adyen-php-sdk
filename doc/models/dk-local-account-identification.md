
# DK Local Account Identification

## Structure

`DKLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 4-10 digits bank account number (Kontonummer) (without separators or whitespace).<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `10` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bankCode` | `string` | Required | The 4-digit bank code (Registreringsnummer) (without separators or whitespace).<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `4` | getBankCode(): string | setBankCode(string bankCode): void |
| `type` | `string` | Required, Constant | **dkLocal**<br><br>**Value**: `'dkLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\DKLocalAccountIdentificationBuilder;

$dKLocalAccountIdentification = DKLocalAccountIdentificationBuilder::init(
    'accountNumber8',
    'bankCode4'
)->build();
```

