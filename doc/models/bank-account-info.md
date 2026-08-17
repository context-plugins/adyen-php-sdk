
# Bank Account Info

## Structure

`BankAccountInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountIdentification` | [AULocalAccountIdentification](../../doc/models/au-local-account-identification.md)\|[CALocalAccountIdentification](../../doc/models/ca-local-account-identification.md)\|[CZLocalAccountIdentification](../../doc/models/cz-local-account-identification.md)\|[DKLocalAccountIdentification](../../doc/models/dk-local-account-identification.md)\|[HKLocalAccountIdentification](../../doc/models/hk-local-account-identification.md)\|[HULocalAccountIdentification](../../doc/models/hu-local-account-identification.md)\|[IbanAccountIdentification](../../doc/models/iban-account-identification.md)\|[NOLocalAccountIdentification](../../doc/models/no-local-account-identification.md)\|[NZLocalAccountIdentification](../../doc/models/nz-local-account-identification.md)\|[NumberAndBicAccountIdentification](../../doc/models/number-and-bic-account-identification.md)\|[PLLocalAccountIdentification](../../doc/models/pl-local-account-identification.md)\|[SELocalAccountIdentification](../../doc/models/se-local-account-identification.md)\|[SGLocalAccountIdentification](../../doc/models/sg-local-account-identification.md)\|[UKLocalAccountIdentification](../../doc/models/uk-local-account-identification.md)\|[USLocalAccountIdentification](../../doc/models/us-local-account-identification.md)\|null | Optional | This is a container for one-of cases. | getAccountIdentification(): | setAccountIdentification( accountIdentification): void |
| `accountType` | `?string` | Optional | The type of bank account. | getAccountType(): ?string | setAccountType(?string accountType): void |
| `bankName` | `?string` | Optional | The name of the banking institution where the bank account is held. | getBankName(): ?string | setBankName(?string bankName): void |
| `countryCode` | `?string` | Optional | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code where the bank account is registered. For example, **NL**. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `trustedSource` | `?bool` | Optional, Read-only | Identifies if the bank account was created through [instant bank verification](https://docs.adyen.com/release-notes/platforms-and-financial-products#releaseNote=2023-05-08-hosted-onboarding). | getTrustedSource(): ?bool | setTrustedSource(?bool trustedSource): void |

## Example

```php
use AdyenLib\Models\Builders\BankAccountInfoBuilder;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;

$bankAccountInfo = BankAccountInfoBuilder::init()
    ->accountIdentification(
        AULocalAccountIdentificationBuilder::init(
            'accountNumber4',
            'bsbCode8'
        )->build()
    )
    ->accountType('accountType8')
    ->bankName('bankName4')
    ->countryCode('countryCode4')
    ->build();
```

