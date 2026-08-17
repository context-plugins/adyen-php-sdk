
# Transaction

## Structure

`Transaction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolder` | [`ResourceReference3`](../../doc/models/resource-reference-3.md) | Required | Contains information about the account holder associated with the `balanceAccount`. | getAccountHolder(): ResourceReference3 | setAccountHolder(ResourceReference3 accountHolder): void |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains information about the amount of the transaction. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `balanceAccount` | [`ResourceReference4`](../../doc/models/resource-reference-4.md) | Required | Contains information about the balance account involved in the transaction. | getBalanceAccount(): ResourceReference4 | setBalanceAccount(ResourceReference4 balanceAccount): void |
| `balancePlatform` | `string` | Required | The unique identifier of the balance platform. | getBalancePlatform(): string | setBalancePlatform(string balancePlatform): void |
| `bookingDate` | `DateTime` | Required | The date the transaction was booked into the balance account. | getBookingDate(): \DateTime | setBookingDate(\DateTime bookingDate): void |
| `creationDate` | `?DateTime` | Optional | The date and time when the event was triggered, in ISO 8601 extended format. For example, **2025-03-19T10:15:30+01:00**. | getCreationDate(): ?\DateTime | setCreationDate(?\DateTime creationDate): void |
| `description` | `?string` | Optional | The `description` from the `/transfers` request. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `string` | Required | The unique identifier of the transaction. | getId(): string | setId(string id): void |
| `paymentInstrument` | [`?PaymentInstrument21`](../../doc/models/payment-instrument-21.md) | Optional | Contains information about the payment instrument that was used for the transaction. | getPaymentInstrument(): ?PaymentInstrument21 | setPaymentInstrument(?PaymentInstrument21 paymentInstrument): void |
| `referenceForBeneficiary` | `?string` | Optional | The reference sent to or received from the counterparty.<br><br>* For outgoing funds, this is the [`referenceForBeneficiary`](https://docs.adyen.com/api-explorer/#/transfers/latest/post/transfers__resParam_referenceForBeneficiary) from the  [`/transfers`](https://docs.adyen.com/api-explorer/#/transfers/latest/post/transfers__reqParam_referenceForBeneficiary) request.<br><br>* For incoming funds, this is the reference from the sender. | getReferenceForBeneficiary(): ?string | setReferenceForBeneficiary(?string referenceForBeneficiary): void |
| `status` | [`string(Status72Enum)`](../../doc/models/status-72-enum.md) | Required | The status of the transaction.<br><br>Possible values:<br><br>* **pending**: The transaction is still pending.<br><br>* **booked**: The transaction has been booked to the balance account. | getStatus(): string | setStatus(string status): void |
| `transfer` | [`?TransferView2`](../../doc/models/transfer-view-2.md) | Optional | Contains information about the transfer related to the transaction. | getTransfer(): ?TransferView2 | setTransfer(?TransferView2 transfer): void |
| `valueDate` | `DateTime` | Required | The date the transfer amount becomes available in the balance account. | getValueDate(): \DateTime | setValueDate(\DateTime valueDate): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionBuilder;
use AdyenLib\Models\Builders\ResourceReference3Builder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\ResourceReference4Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Status72Enum;
use AdyenLib\Models\Builders\PaymentInstrument21Builder;
use AdyenLib\Models\Builders\TransferView2Builder;
use AdyenLib\Models\Builders\BankCategoryDataBuilder;
use AdyenLib\Models\Priority1Enum;
use AdyenLib\Models\Type310Enum;

$transaction = TransactionBuilder::init(
    ResourceReference3Builder::init()
        ->description('description0')
        ->id('id0')
        ->reference('reference4')
        ->build(),
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    ResourceReference4Builder::init()
        ->description('description2')
        ->id('id2')
        ->reference('reference2')
        ->build(),
    'balancePlatform0',
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    'id8',
    Status72Enum::BOOKED,
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
)
    ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->description('description8')
    ->paymentInstrument(
        PaymentInstrument21Builder::init()
            ->description('description0')
            ->id('id0')
            ->reference('reference6')
            ->tokenType('tokenType6')
            ->build()
    )
    ->referenceForBeneficiary('referenceForBeneficiary2')
    ->transfer(
        TransferView2Builder::init(
            'reference4'
        )
            ->categoryData(
                BankCategoryDataBuilder::init()
                    ->priority(Priority1Enum::INSTANT)
                    ->type(Type310Enum::BANK)
                    ->build()
            )
            ->id('id8')
            ->build()
    )
    ->build();
```

