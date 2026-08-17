
# Bank Account Identification Validation Request

## Structure

`BankAccountIdentificationValidationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountIdentification` | [AULocalAccountIdentification](../../doc/models/au-local-account-identification.md)\|[BRLocalAccountIdentification](../../doc/models/br-local-account-identification.md)\|[CALocalAccountIdentification](../../doc/models/ca-local-account-identification.md)\|[CZLocalAccountIdentification](../../doc/models/cz-local-account-identification.md)\|[DKLocalAccountIdentification](../../doc/models/dk-local-account-identification.md)\|[HKLocalAccountIdentification](../../doc/models/hk-local-account-identification.md)\|[HULocalAccountIdentification](../../doc/models/hu-local-account-identification.md)\|[IbanAccountIdentification](../../doc/models/iban-account-identification.md)\|[NOLocalAccountIdentification](../../doc/models/no-local-account-identification.md)\|[NZLocalAccountIdentification](../../doc/models/nz-local-account-identification.md)\|[NumberAndBicAccountIdentification](../../doc/models/number-and-bic-account-identification.md)\|[PLLocalAccountIdentification](../../doc/models/pl-local-account-identification.md)\|[SELocalAccountIdentification](../../doc/models/se-local-account-identification.md)\|[SGLocalAccountIdentification](../../doc/models/sg-local-account-identification.md)\|[UKLocalAccountIdentification](../../doc/models/uk-local-account-identification.md)\|[USLocalAccountIdentification](../../doc/models/us-local-account-identification.md) | Required | This is a container for one-of cases. | getAccountIdentification(): | setAccountIdentification( accountIdentification): void |

## Example

```php
use AdyenLib\Models\Builders\BankAccountIdentificationValidationRequestBuilder;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;

$bankAccountIdentificationValidationRequest = BankAccountIdentificationValidationRequestBuilder::init(
    AULocalAccountIdentificationBuilder::init(
        'accountNumber4',
        'bsbCode8'
    )->build()
)->build();
```

