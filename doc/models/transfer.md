
# Transfer

## Structure

`Transfer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolder` | [`?ResourceReference5`](../../doc/models/resource-reference-5.md) | Optional | The account holder associated with the balance account involved in the transfer. | getAccountHolder(): ?ResourceReference5 | setAccountHolder(?ResourceReference5 accountHolder): void |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The amount of the transfer. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `balanceAccount` | [`?ResourceReference1`](../../doc/models/resource-reference-1.md) | Optional | Contains information about the balance account involved in the transfer. | getBalanceAccount(): ?ResourceReference1 | setBalanceAccount(?ResourceReference1 balanceAccount): void |
| `category` | [`string(Category3Enum)`](../../doc/models/category-3-enum.md) | Required | The category of the transfer.<br><br>Possible values:<br><br>- **bank**: A transfer involving a [transfer instrument](https://docs.adyen.com/api-explorer/legalentity/latest/post/transferInstruments#responses-200-id) or a bank account.<br><br>- **card**: A transfer involving a third-party card.<br><br>- **internal**: A transfer between [balance accounts](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/balanceAccounts#responses-200-id) within your platform.<br><br>- **issuedCard**: A transfer initiated by an Adyen-issued card.<br><br>- **platformPayment**: Funds movements related to payments that are acquired for your users.<br><br>- **topUp**: An incoming transfer initiated by your user to top up their balance account. | getCategory(): string | setCategory(string category): void |
| `categoryData` | [BankCategoryData](../../doc/models/bank-category-data.md)\|[InternalCategoryData](../../doc/models/internal-category-data.md)\|[IssuedCard](../../doc/models/issued-card.md)\|[PlatformPayment](../../doc/models/platform-payment.md)\|null | Optional | This is a container for one-of cases. | getCategoryData(): | setCategoryData( categoryData): void |
| `counterparty` | [`CounterpartyV31`](../../doc/models/counterparty-v31.md) | Required | The other party in the transfer. | getCounterparty(): CounterpartyV31 | setCounterparty(CounterpartyV31 counterparty): void |
| `createdAt` | `?DateTime` | Optional | The date and time when the transfer was created, in ISO 8601 extended format. For example, **2020-12-18T10:15:30+01:00**. | getCreatedAt(): ?\DateTime | setCreatedAt(?\DateTime createdAt): void |
| `creationDate` | `?DateTime` | Optional | The date and time when the event was triggered, in ISO 8601 extended format. For example, **2020-12-18T10:15:30+01:00**. | getCreationDate(): ?\DateTime | setCreationDate(?\DateTime creationDate): void |
| `description` | `?string` | Optional | Your description for the transfer. It is used by most banks as the transfer description. We recommend sending a maximum of 140 characters, otherwise the description may be truncated.<br><br>Supported characters: **[a-z] [A-Z] [0-9] / - ?** **: ( ) . , ' + Space**<br><br>Supported characters for **regular** and **fast** transfers to a US counterparty: **[a-z] [A-Z] [0-9] & $ % # @** **~ = + - _ ' " ! ?** | getDescription(): ?string | setDescription(?string description): void |
| `directDebitInformation` | [`?DirectDebitInformation1`](../../doc/models/direct-debit-information-1.md) | Optional | The details of the direct debit. | getDirectDebitInformation(): ?DirectDebitInformation1 | setDirectDebitInformation(?DirectDebitInformation1 directDebitInformation): void |
| `direction` | [`?string(DirectionEnum)`](../../doc/models/direction-enum.md) | Optional | The direction of the transfer.<br><br>Possible values: **incoming**, **outgoing**. | getDirection(): ?string | setDirection(?string direction): void |
| `executionDate` | [`?ExecutionDate1`](../../doc/models/execution-date-1.md) | Optional | Contains information about the date when the transfer will be processed. The execution date must be within 30 days of the current date.<br><br>Until the execution date:<br><br>- The `status` of the transfer remains as **received**.<br>- The `reason` of the transfer remains as **pending**. | getExecutionDate(): ?ExecutionDate1 | setExecutionDate(?ExecutionDate1 executionDate): void |
| `id` | `?string` | Optional | The ID of the resource. | getId(): ?string | setId(?string id): void |
| `paymentInstrument` | [`?PaymentInstrument3`](../../doc/models/payment-instrument-3.md) | Optional | Contains information about the payment instrument used in the transfer. | getPaymentInstrument(): ?PaymentInstrument3 | setPaymentInstrument(?PaymentInstrument3 paymentInstrument): void |
| `reason` | [`?string(Reason2Enum)`](../../doc/models/reason-2-enum.md) | Optional | Additional information about the status of the transfer. | getReason(): ?string | setReason(?string reason): void |
| `reference` | `?string` | Optional | Your reference for the transfer, used internally within your platform. If you don't provide this in the request, Adyen generates a unique reference.<br><br>**Constraints**: *Maximum Length*: `80` | getReference(): ?string | setReference(?string reference): void |
| `referenceForBeneficiary` | `?string` | Optional | A reference that is sent to the recipient. This reference is also sent in all webhooks related to the transfer, so you can use it to track statuses for both the source and recipient of funds.<br><br>Supported characters: **a-z**, **A-Z**, **0-9**.The maximum length depends on the `category`.<br><br>- **internal**: 80 characters<br><br>- **bank**: 35 characters when transferring to an IBAN, 15 characters for others. | getReferenceForBeneficiary(): ?string | setReferenceForBeneficiary(?string referenceForBeneficiary): void |
| `review` | [`?TransferReview1`](../../doc/models/transfer-review-1.md) | Optional | Contains status updates related to additional reviews. | getReview(): ?TransferReview1 | setReview(?TransferReview1 review): void |
| `status` | [`string(Status51Enum)`](../../doc/models/status-51-enum.md) | Required | The result of the transfer.<br><br>For example:<br><br>- **received**: an outgoing transfer request is created.<br>- **refused**: the transfer request is rejected by Adyen for one of the following reasons:<br>  - Transfer limit exceeded.<br>  - Transaction rule requirements violated.<br>- **authorised**: the transfer request is authorized and the funds are reserved.<br>- **booked**: the funds are deducted from your user's balance account.<br>- **failed**: the transfer is rejected by the counterparty's bank.<br>- **returned**: the transfer is returned by the counterparty's bank. | getStatus(): string | setStatus(string status): void |
| `type` | [`?string(Type83Enum)`](../../doc/models/type-83-enum.md) | Optional | The type of transfer or transaction. For example, **refund**, **payment**, **internalTransfer**, **bankTransfer**. | getType(): ?string | setType(?string type): void |
| `ultimateParty` | [`?UltimatePartyIdentification1`](../../doc/models/ultimate-party-identification-1.md) | Optional | The ultimate sender of the funds of the transfer (ultimate debtor). | getUltimateParty(): ?UltimatePartyIdentification1 | setUltimateParty(?UltimatePartyIdentification1 ultimateParty): void |

## Example

```php
use AdyenLib\Models\Builders\TransferBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Category3Enum;
use AdyenLib\Models\Builders\CounterpartyV31Builder;
use AdyenLib\Models\Builders\BankAccountV31Builder;
use AdyenLib\Models\Builders\PartyIdentification3Builder;
use AdyenLib\Models\Builders\Address12Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;
use AdyenLib\Models\Builders\Card12Builder;
use AdyenLib\Models\Builders\PartyIdentification1Builder;
use AdyenLib\Models\Builders\CardIdentification3Builder;
use AdyenLib\Models\Builders\MerchantData2Builder;
use AdyenLib\Models\Builders\NameLocation2Builder;
use AdyenLib\Models\Status51Enum;
use AdyenLib\Models\Builders\ResourceReference5Builder;
use AdyenLib\Models\Builders\ResourceReference1Builder;
use AdyenLib\Models\Builders\BankCategoryDataBuilder;
use AdyenLib\Models\Priority1Enum;
use AdyenLib\Models\Type310Enum;

$transfer = TransferBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    Category3Enum::PLATFORMPAYMENT,
    CounterpartyV31Builder::init()
        ->balanceAccountId('balanceAccountId0')
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
            MerchantData2Builder::init()
                ->acquirerId('acquirerId6')
                ->mcc('mcc4')
                ->merchantId('merchantId0')
                ->nameLocation(
                    NameLocation2Builder::init()
                        ->city('city6')
                        ->country('country8')
                        ->countryOfOrigin('countryOfOrigin0')
                        ->name('name4')
                        ->rawData('rawData0')
                        ->build()
                )
                ->postalCode('postalCode6')
                ->build()
        )
        ->transferInstrumentId('transferInstrumentId4')
        ->build(),
    Status51Enum::BOOKED
)
    ->accountHolder(
        ResourceReference5Builder::init()
            ->description('description0')
            ->id('id0')
            ->reference('reference4')
            ->build()
    )
    ->balanceAccount(
        ResourceReference1Builder::init()
            ->description('description2')
            ->id('id2')
            ->reference('reference2')
            ->build()
    )
    ->categoryData(
        BankCategoryDataBuilder::init()
            ->priority(Priority1Enum::INSTANT)
            ->type(Type310Enum::BANK)
            ->build()
    )
    ->createdAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

