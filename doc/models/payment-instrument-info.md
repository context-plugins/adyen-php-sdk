
# Payment Instrument Info

## Structure

`PaymentInstrumentInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountId` | `string` | Required | The unique identifier of the [balance account](https://docs.adyen.com/api-explorer/#/balanceplatform/v1/post/balanceAccounts__resParam_id) associated with the payment instrument. | getBalanceAccountId(): string | setBalanceAccountId(string balanceAccountId): void |
| `bankAccount` | [`?BankAccountModel1`](../../doc/models/bank-account-model-1.md) | Optional | Contains the business account details. | getBankAccount(): ?BankAccountModel1 | setBankAccount(?BankAccountModel1 bankAccount): void |
| `card` | [`?CardInfo1`](../../doc/models/card-info-1.md) | Optional | Contains information about the card. Required when you create a payment instrument of `type` **card**. | getCard(): ?CardInfo1 | setCard(?CardInfo1 card): void |
| `description` | `?string` | Optional | Your description for the payment instrument, maximum 300 characters.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): ?string | setDescription(?string description): void |
| `issuingCountryCode` | `string` | Required | The two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code where the payment instrument is issued. For example, **NL** or **US**. | getIssuingCountryCode(): string | setIssuingCountryCode(string issuingCountryCode): void |
| `paymentInstrumentGroupId` | `?string` | Optional | The unique identifier of the [payment instrument group](https://docs.adyen.com/api-explorer/#/balanceplatform/v1/post/paymentInstrumentGroups__resParam_id) to which the payment instrument belongs. | getPaymentInstrumentGroupId(): ?string | setPaymentInstrumentGroupId(?string paymentInstrumentGroupId): void |
| `reference` | `?string` | Optional | Your reference for the payment instrument, maximum 150 characters.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `status` | [`?string(Status10Enum)`](../../doc/models/status-10-enum.md) | Optional | The status of the payment instrument. If a status is not specified when creating a payment instrument, it is set to **active** by default. However, there can be exceptions for cards based on the `card.formFactor` and the `issuingCountryCode`. For example, when issuing physical cards in the US, the default status is **inactive**.<br><br>Possible values:<br><br>* **active**:  The payment instrument is active and can be used to make payments.<br><br>* **inactive**: The payment instrument is inactive and cannot be used to make payments.<br><br>* **suspended**: The payment instrument is suspended, either because it was stolen or lost.<br><br>* **closed**: The payment instrument is permanently closed. This action cannot be undone. | getStatus(): ?string | setStatus(?string status): void |
| `statusComment` | `?string` | Optional | The status comment provides additional information for the statusReason of the payment instrument. | getStatusComment(): ?string | setStatusComment(?string statusComment): void |
| `statusReason` | [`?string(StatusReasonEnum)`](../../doc/models/status-reason-enum.md) | Optional | The reason for the status of the payment instrument.<br><br>Possible values: **accountClosure**, **damaged**, **endOfLife**, **expired**, **lost**, **stolen**, **suspectedFraud**, **transactionRule**, **other**.<br>If the reason is **other**, you must also send the `statusComment` parameter describing the status change. | getStatusReason(): ?string | setStatusReason(?string statusReason): void |
| `type` | [`string(Type111Enum)`](../../doc/models/type-111-enum.md) | Required | The type of payment instrument.<br><br>Possible values: **card**, **bankAccount**. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentInfoBuilder;
use AdyenLib\Models\Type111Enum;
use AdyenLib\Models\Builders\BankAccountModel1Builder;
use AdyenLib\Models\FormFactorEnum;
use AdyenLib\Models\Builders\CardInfo1Builder;
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

$paymentInstrumentInfo = PaymentInstrumentInfoBuilder::init(
    'balanceAccountId2',
    'issuingCountryCode2',
    Type111Enum::BANKACCOUNT
)
    ->bankAccount(
        BankAccountModel1Builder::init()
            ->formFactor(FormFactorEnum::UNKNOWN)
            ->build()
    )
    ->card(
        CardInfo1Builder::init(
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
            ->threeDSecure('threeDSecure8')
            ->usage('usage4')
            ->build()
    )
    ->description('description0')
    ->paymentInstrumentGroupId('paymentInstrumentGroupId0')
    ->reference('reference4')
    ->build();
```

