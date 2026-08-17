
# RIX Account Identifier

## Structure

`RIXAccountIdentifier`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The account number of the bank account. | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `clearingNumber` | `string` | Required | The 4- to 5-digit clearing number, without separators or whitespace. | getClearingNumber(): string | setClearingNumber(string clearingNumber): void |

## Example

```php
use AdyenLib\Models\Builders\RIXAccountIdentifierBuilder;

$rIXAccountIdentifier = RIXAccountIdentifierBuilder::init(
    'accountNumber8',
    'clearingNumber0'
)->build();
```

