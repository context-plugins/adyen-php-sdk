
# Bank Account Detail

The details of the bank account to where a payout was made.

## Structure

`BankAccountDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `?string` | Optional | The bank account number (without separators).<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getAccountNumber(): ?string | setAccountNumber(?string accountNumber): void |
| `accountType` | `?string` | Optional | The type of bank account.<br>Only applicable to bank accounts held in the USA.<br>The permitted values are: `checking`, `savings`.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getAccountType(): ?string | setAccountType(?string accountType): void |
| `bankAccountName` | `?string` | Optional | The name of the bank account. | getBankAccountName(): ?string | setBankAccountName(?string bankAccountName): void |
| `bankAccountReference` | `?string` | Optional | Merchant reference to the bank account. | getBankAccountReference(): ?string | setBankAccountReference(?string bankAccountReference): void |
| `bankAccountUUID` | `?string` | Optional | The unique identifier (UUID) of the Bank Account.<br><br>> If, during an account holder create or update request, this field is left blank (but other fields provided), a new Bank Account will be created with a procedurally-generated UUID.<br><br>> If, during an account holder create request, a UUID is provided, the creation of the Bank Account will fail while the creation of the account holder will continue.<br><br>> If, during an account holder update request, a UUID that is not correlated with an existing Bank Account is provided, the update of the account holder will fail.<br><br>> If, during an account holder update request, a UUID that is correlated with an existing Bank Account is provided, the existing Bank Account will be updated. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `bankBicSwift` | `?string` | Optional | The bank identifier code.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getBankBicSwift(): ?string | setBankBicSwift(?string bankBicSwift): void |
| `bankCity` | `?string` | Optional | The city in which the bank branch is located.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getBankCity(): ?string | setBankCity(?string bankCity): void |
| `bankCode` | `?string` | Optional | The bank code of the banking institution with which the bank account is registered.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getBankCode(): ?string | setBankCode(?string bankCode): void |
| `bankName` | `?string` | Optional | The name of the banking institution with which the bank account is held.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getBankName(): ?string | setBankName(?string bankName): void |
| `branchCode` | `?string` | Optional | The branch code of the branch under which the bank account is registered. The value to be specified in this parameter depends on the country of the bank account:<br><br>* United States - Routing number<br>* United Kingdom - Sort code<br>* Germany - Bankleitzahl<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getBranchCode(): ?string | setBranchCode(?string branchCode): void |
| `checkCode` | `?string` | Optional | The check code of the bank account.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getCheckCode(): ?string | setCheckCode(?string checkCode): void |
| `countryCode` | `?string` | Optional | The two-letter country code in which the bank account is registered.<br><br>> The permitted country codes are defined in ISO-3166-1 alpha-2 (e.g. 'NL').<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `currencyCode` | `?string` | Optional | The currency in which the bank account deals.<br><br>> The permitted currency codes are defined in ISO-4217 (e.g. 'EUR'). | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |
| `iban` | `?string` | Optional | The international bank account number.<br><br>> The IBAN standard is defined in ISO-13616.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getIban(): ?string | setIban(?string iban): void |
| `ownerCity` | `?string` | Optional | The city of residence of the bank account owner.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getOwnerCity(): ?string | setOwnerCity(?string ownerCity): void |
| `ownerCountryCode` | `?string` | Optional | The country code of the country of residence of the bank account owner.<br><br>> The permitted country codes are defined in ISO-3166-1 alpha-2 (e.g. 'NL').<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getOwnerCountryCode(): ?string | setOwnerCountryCode(?string ownerCountryCode): void |
| `ownerDateOfBirth` | `?string` | Optional | The date of birth of the bank account owner.<br>The date should be in ISO-8601 format yyyy-mm-dd (e.g. 2000-01-31). | getOwnerDateOfBirth(): ?string | setOwnerDateOfBirth(?string ownerDateOfBirth): void |
| `ownerHouseNumberOrName` | `?string` | Optional | The house name or number of the residence of the bank account owner.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getOwnerHouseNumberOrName(): ?string | setOwnerHouseNumberOrName(?string ownerHouseNumberOrName): void |
| `ownerName` | `?string` | Optional | The name of the bank account owner.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getOwnerName(): ?string | setOwnerName(?string ownerName): void |
| `ownerNationality` | `?string` | Optional | The country code of the country of nationality of the bank account owner.<br><br>> The permitted country codes are defined in ISO-3166-1 alpha-2 (e.g. 'NL').<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getOwnerNationality(): ?string | setOwnerNationality(?string ownerNationality): void |
| `ownerPostalCode` | `?string` | Optional | The postal code of the residence of the bank account owner.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getOwnerPostalCode(): ?string | setOwnerPostalCode(?string ownerPostalCode): void |
| `ownerState` | `?string` | Optional | The state of residence of the bank account owner.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getOwnerState(): ?string | setOwnerState(?string ownerState): void |
| `ownerStreet` | `?string` | Optional | The street name of the residence of the bank account owner.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getOwnerStreet(): ?string | setOwnerStreet(?string ownerStreet): void |
| `primaryAccount` | `?bool` | Optional | If set to true, the bank account is a primary account. | getPrimaryAccount(): ?bool | setPrimaryAccount(?bool primaryAccount): void |
| `taxId` | `?string` | Optional | The tax ID number.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getTaxId(): ?string | setTaxId(?string taxId): void |
| `urlForVerification` | `?string` | Optional | The URL to be used for bank account verification.<br>This may be generated on bank account creation.<br><br>> Refer to [Required information](https://docs.adyen.com/classic-platforms/verification-process/required-information) for details on field requirements. | getUrlForVerification(): ?string | setUrlForVerification(?string urlForVerification): void |

## Example

```php
use AdyenLib\Models\Builders\BankAccountDetailBuilder;

$bankAccountDetail = BankAccountDetailBuilder::init()
    ->accountNumber('accountNumber8')
    ->accountType('accountType4')
    ->bankAccountName('bankAccountName4')
    ->bankAccountReference('bankAccountReference4')
    ->bankAccountUUID('bankAccountUUID0')
    ->build();
```

