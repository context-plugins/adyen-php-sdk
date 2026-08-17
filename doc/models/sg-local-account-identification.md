
# SG Local Account Identification

## Structure

`SGLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 4- to 19-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `19` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `bic` | `string` | Required | The bank's 8- or 11-character BIC or SWIFT code.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `11` | getBic(): string | setBic(string bic): void |
| `type` | [`?string(Type82Enum)`](../../doc/models/type-82-enum.md) | Optional | **sgLocal**<br><br>**Default**: `Type82Enum::SGLOCAL` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\SGLocalAccountIdentificationBuilder;
use AdyenLib\Models\Type82Enum;

$sGLocalAccountIdentification = SGLocalAccountIdentificationBuilder::init(
    'accountNumber4',
    'bic8'
)
    ->type(Type82Enum::SGLOCAL)
    ->build();
```

