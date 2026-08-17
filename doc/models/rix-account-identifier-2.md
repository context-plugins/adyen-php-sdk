
# RIX Account Identifier 2

Identifiers relevant for the Rix (Russian Interbank eXchange) system, used for interbank payments within Russia.

## Structure

`RIXAccountIdentifier2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The account number of the bank account. | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `clearingNumber` | `string` | Required | The 4- to 5-digit clearing number, without separators or whitespace. | getClearingNumber(): string | setClearingNumber(string clearingNumber): void |

## Example

```php
use AdyenLib\Models\Builders\RIXAccountIdentifier2Builder;

$rIXAccountIdentifier2 = RIXAccountIdentifier2Builder::init(
    'accountNumber0',
    'clearingNumber2'
)->build();
```

