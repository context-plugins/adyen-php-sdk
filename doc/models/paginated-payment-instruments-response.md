
# Paginated Payment Instruments Response

## Structure

`PaginatedPaymentInstrumentsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hasNext` | `bool` | Required | Indicates whether there are more items on the next page. | getHasNext(): bool | setHasNext(bool hasNext): void |
| `hasPrevious` | `bool` | Required | Indicates whether there are more items on the previous page. | getHasPrevious(): bool | setHasPrevious(bool hasPrevious): void |
| `paymentInstruments` | [`PaymentInstrument1[]`](../../doc/models/payment-instrument-1.md) | Required | List of payment instruments associated with the balance account. | getPaymentInstruments(): array | setPaymentInstruments(array paymentInstruments): void |

## Example

```php
use AdyenLib\Models\Builders\PaginatedPaymentInstrumentsResponseBuilder;
use AdyenLib\Models\Builders\PaymentInstrument1Builder;
use AdyenLib\Models\Type111Enum;
use AdyenLib\Models\Builders\IbanAccountIdentificationBuilder;
use AdyenLib\Models\Builders\BankAccountDetails1Builder;
use AdyenLib\Models\Builders\Card11Builder;
use AdyenLib\Models\FormFactor1Enum;
use AdyenLib\Models\Builders\Authentication1Builder;
use AdyenLib\Models\Builders\Phone11Builder;
use AdyenLib\Models\Type410Enum;
use AdyenLib\Models\Builders\CardConfiguration2Builder;
use AdyenLib\Models\Builders\BulkAddress1Builder;
use AdyenLib\Models\Builders\DeliveryContact1Builder;
use AdyenLib\Models\Builders\StoreLocationBuilder;
use AdyenLib\Models\Builders\NameBuilder;
use AdyenLib\Models\Builders\ViasPhoneNumberBuilder;
use AdyenLib\Models\PhoneTypeEnum;

$paginatedPaymentInstrumentsResponse = PaginatedPaymentInstrumentsResponseBuilder::init(
    false,
    false,
    [
        PaymentInstrument1Builder::init(
            'balanceAccountId0',
            'id8',
            'issuingCountryCode0',
            Type111Enum::BANKACCOUNT
        )
            ->additionalBankAccountIdentifications(
                [
                    IbanAccountIdentificationBuilder::init(
                        'iban6'
                    )
                        ->bic('bic4')
                        ->build(),
                    IbanAccountIdentificationBuilder::init(
                        'iban6'
                    )
                        ->bic('bic4')
                        ->build()
                ]
            )
            ->bankAccount(
                BankAccountDetails1Builder::init(
                    'type2'
                )
                    ->accountNumber('accountNumber4')
                    ->accountType('accountType8')
                    ->branchNumber('branchNumber8')
                    ->formFactor('formFactor2')
                    ->iban('iban2')
                    ->build()
            )
            ->card(
                Card11Builder::init(
                    'brand0',
                    'brandVariant8',
                    'cardholderName8',
                    FormFactor1Enum::PHYSICAL
                )
                    ->authentication(
                        Authentication1Builder::init()
                            ->email('email8')
                            ->password('password2')
                            ->phone(
                                Phone11Builder::init(
                                    'number8',
                                    Type410Enum::LANDLINE
                                )->build()
                            )->build()
                    )
                    ->bin('bin6')
                    ->configuration(
                        CardConfiguration2Builder::init(
                            'configurationProfileId6'
                        )
                            ->activation('activation2')
                            ->activationUrl('activationUrl8')
                            ->bulkAddress(
                                BulkAddress1Builder::init(
                                    'country0'
                                )
                                    ->city('city6')
                                    ->company('company6')
                                    ->email('email0')
                                    ->houseNumberOrName('houseNumberOrName4')
                                    ->line1('line18')
                                    ->build()
                            )
                            ->cardImageId('cardImageId0')
                            ->carrier('carrier8')
                            ->build()
                    )
                    ->cvc('cvc0')
                    ->deliveryContact(
                        DeliveryContact1Builder::init(
                            StoreLocationBuilder::init(
                                'country0'
                            )
                                ->city('city6')
                                ->line1('line18')
                                ->line2('line20')
                                ->line3('line38')
                                ->postalCode('postalCode8')
                                ->build(),
                            NameBuilder::init(
                                'firstName4',
                                'lastName4'
                            )->build()
                        )
                            ->company('company4')
                            ->email('email0')
                            ->fullPhoneNumber('fullPhoneNumber0')
                            ->phoneNumber(
                                ViasPhoneNumberBuilder::init()
                                    ->phoneCountryCode('phoneCountryCode8')
                                    ->phoneNumber('phoneNumber0')
                                    ->phoneType(PhoneTypeEnum::FAX)
                                    ->build()
                            )
                            ->webAddress('webAddress4')
                            ->build()
                    )
                    ->build()
            )
            ->description('description2')
            ->paymentInstrumentGroupId('paymentInstrumentGroupId2')
            ->build()
    ]
)->build();
```

