
# SE Local Account Identification 1

## Structure

`SELocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 7- to 10-digit bank account number ([Bankkontonummer](https://sv.wikipedia.org/wiki/Bankkonto)), without the clearing number, separators, or whitespace.<br><br>**Constraints**: *Minimum Length*: `7`, *Maximum Length*: `10` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `clearingNumber` | `string` | Required | The 4- to 5-digit clearing number ([Clearingnummer](https://sv.wikipedia.org/wiki/Clearingnummer)), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `5` | getClearingNumber(): string | setClearingNumber(string clearingNumber): void |

## Example

```php
use AdyenLib\Models\Builders\SELocalAccountIdentification1Builder;

$sELocalAccountIdentification1 = SELocalAccountIdentification1Builder::init(
    'accountNumber8',
    'clearingNumber0'
)
    ->type('seLocal')
    ->build();
```

