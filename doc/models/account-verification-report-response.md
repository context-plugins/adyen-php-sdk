
# Account Verification Report Response

## Structure

`AccountVerificationReportResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accounts` | [`VerifiedAccount[]`](../../doc/models/verified-account.md) | Required | A list of bank accounts with their respective information. | getAccounts(): array | setAccounts(array accounts): void |
| `country` | [`string(AccountVerificationCountry1Enum)`](../../doc/models/account-verification-country-1-enum.md) | Required | The location where the third-party individual's bank account is registered. | getCountry(): string | setCountry(string country): void |
| `id` | `string` | Required | The unique identifier for the specific report. | getId(): string | setId(string id): void |

## Example

```php
use AdyenLib\Models\Builders\AccountVerificationReportResponseBuilder;
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
use AdyenLib\Models\AccountVerificationCountry1Enum;

$accountVerificationReportResponse = AccountVerificationReportResponseBuilder::init(
    [
        VerifiedAccountBuilder::init(
            'accountId0',
            'accountName4',
            'accountNumber8',
            AccountType11Enum::CURRENT,
            'currency0',
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
            ->build()
    ],
    AccountVerificationCountry1Enum::LT,
    'id0'
)->build();
```

