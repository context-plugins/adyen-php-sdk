
# Sale to Issuer Data

Sale information intended for the Issuer.
The POI System receives this information and sends it to the Acquirer for the Issuer without any change.

## Structure

`SaleToIssuerData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `statementReference` | `?string` | Optional | Label to print on the bank statement.<br><br>**Constraints**: *Pattern*: `^.+$` | getStatementReference(): ?string | setStatementReference(?string statementReference): void |

## Example

```php
use AdyenLib\Models\Builders\SaleToIssuerDataBuilder;

$saleToIssuerData = SaleToIssuerDataBuilder::init()
    ->statementReference('StatementReference0')
    ->build();
```

