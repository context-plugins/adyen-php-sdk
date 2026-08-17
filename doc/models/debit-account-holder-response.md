
# Debit Account Holder Response

## Structure

`DebitAccountHolderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `?string` | Optional | The code of the account holder. | getAccountHolderCode(): ?string | setAccountHolderCode(?string accountHolderCode): void |
| `bankAccountUUID` | `?string` | Optional | The Adyen-generated unique alphanumeric identifier (UUID) of the account holder's bank account. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `merchantReferences` | `?(string[])` | Optional | List of the `reference` values from the `split` array in the request. | getMerchantReferences(): ?array | setMerchantReferences(?array merchantReferences): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\DebitAccountHolderResponseBuilder;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$debitAccountHolderResponse = DebitAccountHolderResponseBuilder::init()
    ->accountHolderCode('accountHolderCode2')
    ->bankAccountUUID('bankAccountUUID8')
    ->invalidFields(
        [
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build()
        ]
    )
    ->merchantReferences(
        [
            'merchantReferences7',
            'merchantReferences8',
            'merchantReferences9'
        ]
    )
    ->pspReference('pspReference6')
    ->build();
```

