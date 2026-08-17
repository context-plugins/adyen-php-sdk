
# UK Local Account Identification

## Structure

`UKLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 8-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `8` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `sortCode` | `string` | Required | The 6-digit [sort code](https://en.wikipedia.org/wiki/Sort_code), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `6`, *Maximum Length*: `6` | getSortCode(): string | setSortCode(string sortCode): void |
| `type` | `string` | Required, Constant | **ukLocal**<br><br>**Value**: `'ukLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\UKLocalAccountIdentificationBuilder;

$uKLocalAccountIdentification = UKLocalAccountIdentificationBuilder::init(
    'accountNumber0',
    'sortCode0'
)->build();
```

