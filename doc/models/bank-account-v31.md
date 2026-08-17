
# Bank Account V31

Contains information about the counterparty bank account.

## Structure

`BankAccountV31`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolder` | [`PartyIdentification3`](../../doc/models/party-identification-3.md) | Required | Information about the owner of the bank account. | getAccountHolder(): PartyIdentification3 | setAccountHolder(PartyIdentification3 accountHolder): void |
| `accountIdentification` | [AULocalAccountIdentification](../../doc/models/au-local-account-identification.md)\|[BRLocalAccountIdentification](../../doc/models/br-local-account-identification.md)\|[CALocalAccountIdentification](../../doc/models/ca-local-account-identification.md)\|[CZLocalAccountIdentification](../../doc/models/cz-local-account-identification.md)\|[DKLocalAccountIdentification](../../doc/models/dk-local-account-identification.md)\|[HKLocalAccountIdentification](../../doc/models/hk-local-account-identification.md)\|[HULocalAccountIdentification](../../doc/models/hu-local-account-identification.md)\|[IbanAccountIdentification](../../doc/models/iban-account-identification.md)\|[NOLocalAccountIdentification](../../doc/models/no-local-account-identification.md)\|[NZLocalAccountIdentification](../../doc/models/nz-local-account-identification.md)\|[NumberAndBicAccountIdentification](../../doc/models/number-and-bic-account-identification.md)\|[PLLocalAccountIdentification](../../doc/models/pl-local-account-identification.md)\|[SELocalAccountIdentification](../../doc/models/se-local-account-identification.md)\|[SGLocalAccountIdentification](../../doc/models/sg-local-account-identification.md)\|[UKLocalAccountIdentification](../../doc/models/uk-local-account-identification.md)\|[USLocalAccountIdentification](../../doc/models/us-local-account-identification.md) | Required | This is a container for one-of cases. | getAccountIdentification(): | setAccountIdentification( accountIdentification): void |
| `storedPaymentMethodId` | `?string` | Optional | The unique token that identifies the stored bank account details of the counterparty for a payout. | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |

## Example

```php
use AdyenLib\Models\Builders\BankAccountV31Builder;
use AdyenLib\Models\Builders\PartyIdentification3Builder;
use AdyenLib\Models\Builders\Address12Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Type112Enum;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;

$bankAccountV31 = BankAccountV31Builder::init(
    PartyIdentification3Builder::init()
        ->address(
            Address12Builder::init(
                'country0'
            )
                ->city('city6')
                ->line1('line18')
                ->line2('line20')
                ->postalCode('postalCode8')
                ->stateOrProvince('stateOrProvince4')
                ->build()
        )
        ->dateOfBirth(DateTimeHelper::fromSimpleDate('2016-03-13'))
        ->email('email6')
        ->firstName('firstName4')
        ->fullName('fullName0')
        ->type(Type112Enum::UNKNOWN)
        ->build(),
    AULocalAccountIdentificationBuilder::init(
        'accountNumber4',
        'bsbCode8'
    )->build()
)
    ->storedPaymentMethodId('storedPaymentMethodId0')
    ->build();
```

