
# Number and Bic Account Identification 1

## Structure

`NumberAndBicAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The bank account number, without separators or whitespace. The length and format depends on the bank or country.<br><br>**Constraints**: *Maximum Length*: `34` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `additionalBankIdentification` | [`?AdditionalBankIdentification11`](../../doc/models/additional-bank-identification-11.md) | Optional | Additional identification codes of the bank. Some banks may require these identifiers for cross-border transfers. | getAdditionalBankIdentification(): ?AdditionalBankIdentification11 | setAdditionalBankIdentification(?AdditionalBankIdentification11 additionalBankIdentification): void |
| `bic` | `string` | Required | The bank's 8- or 11-character BIC or SWIFT code.<br><br>**Constraints**: *Minimum Length*: `8`, *Maximum Length*: `11` | getBic(): string | setBic(string bic): void |

## Example

```php
use AdyenLib\Models\Builders\NumberAndBicAccountIdentification1Builder;
use AdyenLib\Models\Builders\AdditionalBankIdentification11Builder;
use AdyenLib\Models\AdditionalBankIdentificationTypeEnum;

$numberAndBicAccountIdentification1 = NumberAndBicAccountIdentification1Builder::init(
    'accountNumber6',
    'bic0'
)
    ->type('numberAndBic')
    ->additionalBankIdentification(
        AdditionalBankIdentification11Builder::init()
            ->code('code2')
            ->type(AdditionalBankIdentificationTypeEnum::GBSORTCODE)
            ->build()
    )
    ->build();
```

