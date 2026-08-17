
# Sale to Issuer Data 1

Sale information intended for the Issuer.
Send to the Acquirer if present.

## Structure

`SaleToIssuerData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `statementReference` | `?string` | Optional | Label to print on the bank statement.<br><br>**Constraints**: *Pattern*: `^.+$` | getStatementReference(): ?string | setStatementReference(?string statementReference): void |

## Example

```php
use AdyenLib\Models\Builders\SaleToIssuerData1Builder;

$saleToIssuerData1 = SaleToIssuerData1Builder::init()
    ->statementReference('StatementReference4')
    ->build();
```

