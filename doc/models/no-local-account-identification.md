
# NO Local Account Identification

## Structure

`NOLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 11-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `11`, *Maximum Length*: `11` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `type` | `string` | Required, Constant | **noLocal**<br><br>**Value**: `'noLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\NOLocalAccountIdentificationBuilder;

$nOLocalAccountIdentification = NOLocalAccountIdentificationBuilder::init(
    'accountNumber8'
)->build();
```

