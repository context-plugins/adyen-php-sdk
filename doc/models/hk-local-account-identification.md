
# HK Local Account Identification

## Structure

`HKLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 9- to 17-digit bank account number, without separators or whitespace. Starts with the 3-digit branch code.<br><br>**Constraints**: *Minimum Length*: `9`, *Maximum Length*: `17` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `clearingCode` | `string` | Required | The 3-digit clearing code, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `3`, *Maximum Length*: `3` | getClearingCode(): string | setClearingCode(string clearingCode): void |
| `type` | `string` | Required, Constant | **hkLocal**<br><br>**Value**: `'hkLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\HKLocalAccountIdentificationBuilder;

$hKLocalAccountIdentification = HKLocalAccountIdentificationBuilder::init(
    'accountNumber8',
    'clearingCode4'
)->build();
```

