
# Checkout Bank Account

## Structure

`CheckoutBankAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountType` | [`?string(AccountType1Enum)`](../../doc/models/account-type-1-enum.md) | Optional | The type of the bank account. | getAccountType(): ?string | setAccountType(?string accountType): void |
| `bankAccountNumber` | `?string` | Optional | The bank account number (without separators). | getBankAccountNumber(): ?string | setBankAccountNumber(?string bankAccountNumber): void |
| `bankCity` | `?string` | Optional | The bank city. | getBankCity(): ?string | setBankCity(?string bankCity): void |
| `bankLocationId` | `?string` | Optional | The location id of the bank. The field value is `nil` in most cases. | getBankLocationId(): ?string | setBankLocationId(?string bankLocationId): void |
| `bankName` | `?string` | Optional | The name of the bank. | getBankName(): ?string | setBankName(?string bankName): void |
| `bic` | `?string` | Optional | The [Business Identifier Code](https://en.wikipedia.org/wiki/ISO_9362) (BIC) is the SWIFT address assigned to a bank. The field value is `nil` in most cases. | getBic(): ?string | setBic(?string bic): void |
| `countryCode` | `?string` | Optional | Country code where the bank is located.<br><br>A valid value is an ISO two-character country code (e.g. 'NL'). | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `iban` | `?string` | Optional | The [International Bank Account Number](https://en.wikipedia.org/wiki/International_Bank_Account_Number) (IBAN). | getIban(): ?string | setIban(?string iban): void |
| `ownerName` | `?string` | Optional | The name of the bank account holder.<br>If you submit a name with non-Latin characters, we automatically replace some of them with corresponding Latin characters to meet the FATF recommendations. For example:<br><br>* χ12 is converted to ch12.<br>* üA is converted to euA.<br>* Peter Møller is converted to Peter Mller, because banks don't accept 'ø'.<br>  After replacement, the ownerName must have at least three alphanumeric characters (A-Z, a-z, 0-9), and at least one of them must be a valid Latin character (A-Z, a-z). For example:<br>* John17 - allowed.<br>* J17 - allowed.<br>* 171 - not allowed.<br>* John-7 - allowed.<br><br>> If provided details don't match the required format, the response returns the error message: 203 'Invalid bank account holder name'. | getOwnerName(): ?string | setOwnerName(?string ownerName): void |
| `taxId` | `?string` | Optional | The bank account holder's tax ID. | getTaxId(): ?string | setTaxId(?string taxId): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutBankAccountBuilder;
use AdyenLib\Models\AccountType1Enum;

$checkoutBankAccount = CheckoutBankAccountBuilder::init()
    ->accountType(AccountType1Enum::DEPOSIT)
    ->bankAccountNumber('bankAccountNumber2')
    ->bankCity('bankCity6')
    ->bankLocationId('bankLocationId6')
    ->bankName('bankName2')
    ->build();
```

