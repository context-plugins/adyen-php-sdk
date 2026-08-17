
# Transfer Info

## Structure

`TransferInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The amount of the transfer. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `balanceAccountId` | `?string` | Optional | The unique identifier of the source [balance account](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/balanceAccounts#responses-200-id).<br><br>If you want to make a transfer using a **virtual** **bankAccount** assigned to the balance account, you must specify the [payment instrument ID](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/paymentInstruments#responses-200-id) of the **virtual** **bankAccount**. If you only specify a balance account ID, Adyen uses the default **physical** **bankAccount** payment instrument assigned to the balance account. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `category` | [`string(Category3Enum)`](../../doc/models/category-3-enum.md) | Required | The category of the transfer.<br><br>Possible values:<br><br>- **bank**: A transfer involving a [transfer instrument](https://docs.adyen.com/api-explorer/legalentity/latest/post/transferInstruments#responses-200-id) or a bank account.<br><br>- **card**: A transfer involving a third-party card.<br><br>- **internal**: A transfer between [balance accounts](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/balanceAccounts#responses-200-id) within your platform.<br><br>- **issuedCard**: A transfer initiated by an Adyen-issued card.<br><br>- **platformPayment**: Funds movements related to payments that are acquired for your users.<br><br>- **topUp**: An incoming transfer initiated by your user to top up their balance account. | getCategory(): string | setCategory(string category): void |
| `counterparty` | [`CounterpartyInfoV31`](../../doc/models/counterparty-info-v31.md) | Required | The other party involved in the funds transfer. A bank account, a balance account, a card, or a transfer instrument is required. | getCounterparty(): CounterpartyInfoV31 | setCounterparty(CounterpartyInfoV31 counterparty): void |
| `description` | `?string` | Optional | Your description for the transfer. It is used by most banks as the transfer description. We recommend sending a maximum of 140 characters, otherwise the description may be truncated.<br><br>Supported characters: **[a-z] [A-Z] [0-9] / - ?** **: ( ) . , ' + Space**<br><br>Supported characters for **regular** and **fast** transfers to a US counterparty: **[a-z] [A-Z] [0-9] & $ % # @** **~ = + - _ ' " ! ?**<br><br>**Constraints**: *Maximum Length*: `140` | getDescription(): ?string | setDescription(?string description): void |
| `executionDate` | [`?ExecutionDate3`](../../doc/models/execution-date-3.md) | Optional | The date when the transfer will be processed. This date must be within 30 days of the current date.<br><br>Until the `executionDate`:<br><br>- The `status` of the transfer remains as **received**.<br>- The `reason` of the transfer remains as **pending**. | getExecutionDate(): ?ExecutionDate3 | setExecutionDate(?ExecutionDate3 executionDate): void |
| `paymentInstrumentId` | `?string` | Optional | The unique identifier of the source [payment instrument](https://docs.adyen.com/api-explorer/balanceplatform/latest/post/paymentInstruments#responses-200-id).<br><br>If you want to make a transfer using a **virtual** **bankAccount**, you must specify the payment instrument ID of the **virtual** **bankAccount**. If you only specify a balance account ID, Adyen uses the default **physical** **bankAccount** payment instrument assigned to the balance account. | getPaymentInstrumentId(): ?string | setPaymentInstrumentId(?string paymentInstrumentId): void |
| `priorities` | [`?(string(Priority1Enum)[])`](../../doc/models/priority-1-enum.md) | Optional | The list of priorities for the bank transfer. This sets the speed at which the transfer is sent and the fees that you have to pay. You can provide multiple priorities. Adyen will try to pay out using the priority you list first. If that's not possible, it moves on to the next option in the order of your provided priorities.<br><br>Possible values:<br><br>* **regular**: For normal, low-value transactions.<br><br>* **fast**: A faster way to transfer funds, but the fees are higher. Recommended for high-priority, low-value transactions.<br><br>* **wire**: The fastest way to transfer funds, but this has the highest fees. Recommended for high-priority, high-value transactions.<br><br>* **instant**: For instant funds transfers within the United States and in [SEPA locations](https://www.ecb.europa.eu/paym/integration/retail/sepa/html/index.en.html).<br><br>* **crossBorder**: For high-value transfers to a recipient in a different country.<br><br>* **internal**: For transfers to an Adyen-issued business bank account (by bank account number/IBAN).<br><br>Required for transfers with `category` **bank**. For more details, see [fallback priorities](https://docs.adyen.com/payouts/payout-service/payout-to-users/#fallback-priorities). | getPriorities(): ?array | setPriorities(?array priorities): void |
| `priority` | [`?string(Priority1Enum)`](../../doc/models/priority-1-enum.md) | Optional | The priority for the bank transfer. This sets the speed at which the transfer is sent and the fees that you have to pay. Required for transfers with `category` **bank**.<br><br>Possible values:<br><br>* **regular**: For normal, low-value transactions.<br><br>* **fast**: A faster way to transfer funds, but the fees are higher. Recommended for high-priority, low-value transactions.<br><br>* **wire**: The fastest way to transfer funds, but this has the highest fees. Recommended for high-priority, high-value transactions.<br><br>* **instant**: For instant funds transfers within the United States and in [SEPA locations](https://www.ecb.europa.eu/paym/integration/retail/sepa/html/index.en.html).<br><br>* **crossBorder**: For high-value transfers to a recipient in a different country.<br><br>* **internal**: For transfers to an Adyen-issued business bank account (by bank account number/IBAN). | getPriority(): ?string | setPriority(?string priority): void |
| `reference` | `?string` | Optional | Your reference for the transfer, used internally within your platform. If you don't provide this in the request, Adyen generates a unique reference.<br><br>**Constraints**: *Maximum Length*: `80` | getReference(): ?string | setReference(?string reference): void |
| `referenceForBeneficiary` | `?string` | Optional | A reference that is sent to the recipient. This reference is also sent in all webhooks related to the transfer, so you can use it to track statuses for both parties involved in the funds movement.<br><br>Supported characters: **a-z**, **A-Z**, **0-9**. The maximum length depends on the `category`.<br><br>- **internal**: 80 characters<br><br>- **bank**: 35 characters when transferring to an IBAN, 15 characters for others. | getReferenceForBeneficiary(): ?string | setReferenceForBeneficiary(?string referenceForBeneficiary): void |
| `review` | [`?TransferRequestReview2`](../../doc/models/transfer-request-review-2.md) | Optional | Contains information required for triggering transfer reviews. | getReview(): ?TransferRequestReview2 | setReview(?TransferRequestReview2 review): void |
| `type` | [`?string(Type113Enum)`](../../doc/models/type-113-enum.md) | Optional | The type of transfer.<br><br>Possible values:<br><br>- **bankTransfer**: for push transfers to a transfer instrument or a bank account. The `category` must be **bank**.<br>- **internalTransfer**: for push transfers between balance accounts. The `category` must be **internal**.<br>- **internalDirectDebit**: for pull transfers (direct debits) between balance accounts. The `category` must be **internal**. | getType(): ?string | setType(?string type): void |
| `ultimateParty` | [`?UltimatePartyIdentification1`](../../doc/models/ultimate-party-identification-1.md) | Optional | The ultimate sender of the funds of the transfer (ultimate debtor). | getUltimateParty(): ?UltimatePartyIdentification1 | setUltimateParty(?UltimatePartyIdentification1 ultimateParty): void |

## Example

```php
use AdyenLib\Models\Builders\TransferInfoBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Category3Enum;
use AdyenLib\Models\Builders\CounterpartyInfoV31Builder;
use AdyenLib\Models\Builders\BankAccountV31Builder;
use AdyenLib\Models\Builders\PartyIdentification3Builder;
use AdyenLib\Models\Builders\Address12Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\AULocalAccountIdentificationBuilder;
use AdyenLib\Models\Builders\Card12Builder;
use AdyenLib\Models\Builders\PartyIdentification1Builder;
use AdyenLib\Models\Builders\CardIdentification3Builder;
use AdyenLib\Models\Builders\ExecutionDate3Builder;
use AdyenLib\Models\Priority1Enum;

$transferInfo = TransferInfoBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    Category3Enum::BANK,
    CounterpartyInfoV31Builder::init()
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
        ->transferInstrumentId('transferInstrumentId4')
        ->build()
)
    ->balanceAccountId('balanceAccountId8')
    ->description('description0')
    ->executionDate(
        ExecutionDate3Builder::init()
            ->date(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->timezone('timezone0')
            ->build()
    )
    ->paymentInstrumentId('paymentInstrumentId2')
    ->priorities(
        [
            Priority1Enum::INSTANT
        ]
    )
    ->build();
```

