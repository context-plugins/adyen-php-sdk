
# Transfer Notification Counter Party

## Structure

`TransferNotificationCounterParty`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountId` | `?string` | Optional | The unique identifier of the counterparty [balance account](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/balanceAccounts#responses-200-id). | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `bankAccount` | [`?BankAccountV31`](../../doc/models/bank-account-v31.md) | Optional | Contains information about the counterparty bank account. | getBankAccount(): ?BankAccountV31 | setBankAccount(?BankAccountV31 bankAccount): void |
| `card` | [`?Card12`](../../doc/models/card-12.md) | Optional | Contains information about the counterparty card. | getCard(): ?Card12 | setCard(?Card12 card): void |
| `merchant` | [`?TransferNotificationMerchantData2`](../../doc/models/transfer-notification-merchant-data-2.md) | Optional | Contains information about the merchant. | getMerchant(): ?TransferNotificationMerchantData2 | setMerchant(?TransferNotificationMerchantData2 merchant): void |
| `transferInstrumentId` | `?string` | Optional | The unique identifier of the counterparty [transfer instrument](https://docs.adyen.com/api-explorer/legalentity/latest/post/transferInstruments#responses-200-id). | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\TransferNotificationCounterPartyBuilder;
use AdyenLib\Models\Builders\BankAccountV31Builder;
use AdyenLib\Models\Builders\PartyIdentification3Builder;
use AdyenLib\Models\Builders\Address12Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;
use AdyenLib\Models\Builders\Card12Builder;
use AdyenLib\Models\Builders\PartyIdentification1Builder;
use AdyenLib\Models\Builders\CardIdentification3Builder;
use AdyenLib\Models\Builders\TransferNotificationMerchantData2Builder;

$transferNotificationCounterParty = TransferNotificationCounterPartyBuilder::init()
    ->balanceAccountId('balanceAccountId2')
    ->bankAccount(
        BankAccountV31Builder::init(
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
                ->build(),
            AULocalAccountIdentificationBuilder::init(
                'accountNumber4',
                'bsbCode8'
            )->build()
        )
            ->storedPaymentMethodId('storedPaymentMethodId2')
            ->build()
    )
    ->card(
        Card12Builder::init(
            PartyIdentification1Builder::init()
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
                ->email('email0')
                ->firstName('firstName8')
                ->fullName('fullName6')
                ->build(),
            CardIdentification3Builder::init()
                ->expiryMonth('expiryMonth2')
                ->expiryYear('expiryYear2')
                ->issueNumber('issueNumber0')
                ->number('number6')
                ->startMonth('startMonth8')
                ->build()
        )->build()
    )
    ->merchant(
        TransferNotificationMerchantData2Builder::init()
            ->acquirerId('acquirerId6')
            ->city('city4')
            ->country('country8')
            ->countryCode('countryCode0')
            ->mcc('mcc4')
            ->build()
    )
    ->transferInstrumentId('transferInstrumentId8')
    ->build();
```

