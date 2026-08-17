
# HU Local Account Identification 1

## Structure

`HULocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 24-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `24`, *Maximum Length*: `24` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |

## Example

```php
use AdyenLib\Models\Builders\HULocalAccountIdentification1Builder;

$hULocalAccountIdentification1 = HULocalAccountIdentification1Builder::init(
    'accountNumber6'
)
    ->type('huLocal')
    ->build();
```

