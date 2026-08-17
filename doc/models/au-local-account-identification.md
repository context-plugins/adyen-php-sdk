
# AU Local Account Identification

## Structure

`AULocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `5`, *Maximum Length*: `9` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bsbCode` | `string` | Required | The 6-digit [Bank State Branch (BSB) code](https://en.wikipedia.org/wiki/Bank_state_branch), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `6`, *Maximum Length*: `6` | getBsbCode(): string | setBsbCode(string bsbCode): void |
| `type` | `string` | Required, Constant | **auLocal**<br><br>**Value**: `'auLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;

$aULocalAccountIdentification = AULocalAccountIdentificationBuilder::init(
    'accountNumber0',
    'bsbCode8'
)->build();
```

