
# PL Local Account Identification

## Structure

`PLLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 26-digit bank account number ([Numer rachunku](https://pl.wikipedia.org/wiki/Numer_Rachunku_Bankowego)), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `26`, *Maximum Length*: `26` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `type` | `string` | Required, Constant | **plLocal**<br><br>**Value**: `'plLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\PLLocalAccountIdentificationBuilder;

$pLLocalAccountIdentification = PLLocalAccountIdentificationBuilder::init(
    'accountNumber2'
)->build();
```

