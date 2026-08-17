
# Account Identifiers 1

Contains various codes and details used to uniquely identify the bank account across different regions.

## Structure

`AccountIdentifiers1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ach` | [`?ACHAccountIdentifier1`](../../doc/models/ach-account-identifier-1.md) | Optional | Identifiers relevant for Automated Clearing House (ACH) payments, primarily used in the United States. | getAch(): ?ACHAccountIdentifier1 | setAch(?ACHAccountIdentifier1 ach): void |
| `bacs` | [`?BACSAccountIdentifier2`](../../doc/models/bacs-account-identifier-2.md) | Optional | Identifiers relevant for Bankers' Automated Clearing Services (BACS) payments, primarily used in the United Kingdom. | getBacs(): ?BACSAccountIdentifier2 | setBacs(?BACSAccountIdentifier2 bacs): void |
| `bsb` | [`?BSBAccountIdentifier2`](../../doc/models/bsb-account-identifier-2.md) | Optional | Identifiers relevant for Australian banking, specifically for BSB (Bank-State-Branch) numbers. | getBsb(): ?BSBAccountIdentifier2 | setBsb(?BSBAccountIdentifier2 bsb): void |
| `eft` | [`?EFTAccountIdentifier2`](../../doc/models/eft-account-identifier-2.md) | Optional | Identifiers relevant for Electronic Funds Transfer (EFT) payments, commonly used in Canada. | getEft(): ?EFTAccountIdentifier2 | setEft(?EFTAccountIdentifier2 eft): void |
| `iban` | [`?IBANAccountIdentifier2`](../../doc/models/iban-account-identifier-2.md) | Optional | The international bank account number as defined in the ISO-13616 standard. | getIban(): ?IBANAccountIdentifier2 | setIban(?IBANAccountIdentifier2 iban): void |
| `rix` | [`?RIXAccountIdentifier2`](../../doc/models/rix-account-identifier-2.md) | Optional | Identifiers relevant for the Rix (Russian Interbank eXchange) system, used for interbank payments within Russia. | getRix(): ?RIXAccountIdentifier2 | setRix(?RIXAccountIdentifier2 rix): void |

## Example

```php
use AdyenLib\Models\Builders\AccountIdentifiers1Builder;
use AdyenLib\Models\Builders\ACHAccountIdentifier1Builder;
use AdyenLib\Models\Builders\BACSAccountIdentifier2Builder;
use AdyenLib\Models\Builders\BSBAccountIdentifier2Builder;
use AdyenLib\Models\Builders\EFTAccountIdentifier2Builder;
use AdyenLib\Models\Builders\IBANAccountIdentifier2Builder;

$accountIdentifiers1 = AccountIdentifiers1Builder::init()
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
    )->build();
```

