
# Bank Account Identification Type Requirement

## Structure

`BankAccountIdentificationTypeRequirement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccountIdentificationTypes` | [`?(string(BankAccountIdentificationTypeEnum)[])`](../../doc/models/bank-account-identification-type-enum.md) | Optional | List of bank account identification types: eg.; [iban , numberAndBic] | getBankAccountIdentificationTypes(): ?array | setBankAccountIdentificationTypes(?array bankAccountIdentificationTypes): void |
| `description` | `?string` | Optional | Specifies the bank account details for a particular route per required field in this object depending on the country of the bank account and the currency of the transfer. | getDescription(): ?string | setDescription(?string description): void |
| `type` | `string` | Required, Constant | **bankAccountIdentificationTypeRequirement**<br><br>**Value**: `'bankAccountIdentificationTypeRequirement'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\BankAccountIdentificationTypeRequirementBuilder;
use AdyenLib\Models\BankAccountIdentificationTypeEnum;

$bankAccountIdentificationTypeRequirement = BankAccountIdentificationTypeRequirementBuilder::init()
    ->bankAccountIdentificationTypes(
        [
            BankAccountIdentificationTypeEnum::CZLOCAL
        ]
    )
    ->description('description6')
    ->build();
```

