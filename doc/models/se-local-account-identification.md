
# SE Local Account Identification

## Structure

`SELocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 7- to 10-digit bank account number ([Bankkontonummer](https://sv.wikipedia.org/wiki/Bankkonto)), without the clearing number, separators, or whitespace.<br><br>**Constraints**: *Minimum Length*: `7`, *Maximum Length*: `10` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `clearingNumber` | `string` | Required | The 4- to 5-digit clearing number ([Clearingnummer](https://sv.wikipedia.org/wiki/Clearingnummer)), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `5` | getClearingNumber(): string | setClearingNumber(string clearingNumber): void |
| `type` | `string` | Required, Constant | **seLocal**<br><br>**Value**: `'seLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\SELocalAccountIdentificationBuilder;

$sELocalAccountIdentification = SELocalAccountIdentificationBuilder::init(
    'accountNumber6',
    'clearingNumber6'
)->build();
```

