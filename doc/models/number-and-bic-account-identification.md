
# Number and Bic Account Identification

## Structure

`NumberAndBicAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The bank account number, without separators or whitespace. The length and format depends on the bank or country.<br><br>**Constraints**: *Maximum Length*: `34` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `additionalBankIdentification` | [`?AdditionalBankIdentification1`](../../doc/models/additional-bank-identification-1.md) | Optional | Additional identification codes of the bank. Some banks may require these identifiers for cross-border transfers. | getAdditionalBankIdentification(): ?AdditionalBankIdentification1 | setAdditionalBankIdentification(?AdditionalBankIdentification1 additionalBankIdentification): void |
| `bic` | `string` | Required | The bank's 8- or 11-character BIC or SWIFT code.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `11` | getBic(): string | setBic(string bic): void |
| `type` | `string` | Required, Constant | **numberAndBic**<br><br>**Value**: `'numberAndBic'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\NumberAndBicAccountIdentificationBuilder;
use AdyenLib\Models\Builders\AdditionalBankIdentification1Builder;
use AdyenLib\Models\Type510Enum;

$numberAndBicAccountIdentification = NumberAndBicAccountIdentificationBuilder::init(
    'accountNumber6',
    'bic0'
)
    ->additionalBankIdentification(
        AdditionalBankIdentification1Builder::init()
            ->code('code2')
            ->type(Type510Enum::GBSORTCODE)
            ->build()
    )
    ->build();
```

