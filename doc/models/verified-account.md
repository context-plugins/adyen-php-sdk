
# Verified Account

## Structure

`VerifiedAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountId` | `string` | Required | The unique identifier for the bank account. | getAccountId(): string | setAccountId(string accountId): void |
| `accountName` | `string` | Required | The name of the bank account. This name is assigned by the banking institution, and it describes the type of bank account. | getAccountName(): string | setAccountName(string accountName): void |
| `accountNumber` | `string` | Required | The account number of the bank account. | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `accountType` | [`string(AccountType11Enum)`](../../doc/models/account-type-11-enum.md) | Required | The type of the bank account. Possible values are **CURRENT**, **SAVINGS**, **BUSINESS**, **CREDIT_CARD**, **LOAN**, **UNKNOWN**. | getAccountType(): string | setAccountType(string accountType): void |
| `bankName` | `?string` | Optional | The name of the banking institution where the bank account is held. | getBankName(): ?string | setBankName(?string bankName): void |
| `currency` | `string` | Required | The currency of the funds in the bank account. | getCurrency(): string | setCurrency(string currency): void |
| `identifiers` | [`AccountIdentifiers1`](../../doc/models/account-identifiers-1.md) | Required | Contains various codes and details used to uniquely identify the bank account across different regions. | getIdentifiers(): AccountIdentifiers1 | setIdentifiers(AccountIdentifiers1 identifiers): void |
| `parties` | [`AccountParty[]`](../../doc/models/account-party.md) | Required | Contains details of all parties associated with the report. | getParties(): array | setParties(array parties): void |

## Example

```php
use AdyenLib\Models\Builders\VerifiedAccountBuilder;
use AdyenLib\Models\AccountType11Enum;
use AdyenLib\Models\Builders\AccountIdentifiers1Builder;
use AdyenLib\Models\Builders\ACHAccountIdentifier1Builder;
use AdyenLib\Models\Builders\BACSAccountIdentifier2Builder;
use AdyenLib\Models\Builders\BSBAccountIdentifier2Builder;
use AdyenLib\Models\Builders\EFTAccountIdentifier2Builder;
use AdyenLib\Models\Builders\IBANAccountIdentifier2Builder;
use AdyenLib\Models\Builders\AccountPartyBuilder;
use AdyenLib\Models\Builders\Identity2Builder;
use AdyenLib\Models\PartyRole2Enum;

$verifiedAccount = VerifiedAccountBuilder::init(
    'accountId8',
    'accountName2',
    'accountNumber4',
    AccountType11Enum::CURRENT,
    'currency8',
    AccountIdentifiers1Builder::init()
        ->ach(
            ACHAccountIdentifier1Builder::init(
                'accountNumber4',
                'routingNumber8'
            )
                ->accountLastDigits('accountLastDigits2')
                ->isTokenized(false)
                ->build()
        )
        ->bacs(
            BACSAccountIdentifier2Builder::init(
                'accountNumber2',
                'sortCode8'
            )->build()
        )
        ->bsb(
            BSBAccountIdentifier2Builder::init(
                'accountNumber2',
                'bsbCode0'
            )->build()
        )
        ->eft(
            EFTAccountIdentifier2Builder::init(
                'accountNumber0',
                'branch8',
                'institution2'
            )->build()
        )
        ->iban(
            IBANAccountIdentifier2Builder::init(
                'bban8',
                'bic6',
                'iban8'
            )->build()
        )->build(),
    [
        AccountPartyBuilder::init(
            Identity2Builder::init(
                'fullLegalName2',
                'name4'
            )->build(),
            PartyRole2Enum::HOLDER
        )->build()
    ]
)
    ->bankName('bankName6')
    ->build();
```

