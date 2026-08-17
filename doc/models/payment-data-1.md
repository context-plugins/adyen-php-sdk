
# Payment Data 1

Data related to the payment transaction.
If one data element is present.

## Structure

`PaymentData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?string(PaymentType1Enum)`](../../doc/models/payment-type-1-enum.md) | Optional | Type of payment transaction. Elements requested by the Sale System that are related to the payment only.<br>Possible values:<br><br>* **CashAdvance**<br>* **CashDeposit**<br>* **Completion**<br>* **FirstReservation**<br>* **Instalment**<br>* **IssuerInstalment**<br>* **Normal**<br>* **OneTimeReservation**<br>* **PaidOut**<br>* **Recurring**<br>* **Refund**<br>* **UpdateReservation** | getPaymentType(): ?string | setPaymentType(?string paymentType): void |
| `splitPaymentFlag` | `?bool` | Optional | Indicates if the payment of the Sale transaction is split. Allows the POI to decline payment means that cannot accept split payment.<br><br>**Default**: `false` | getSplitPaymentFlag(): ?bool | setSplitPaymentFlag(?bool splitPaymentFlag): void |
| `requestedValidityDate` | `?DateTime` | Optional | Requested validity date for the reservation. Allows a specific period for the reservation according to the need of the Merchant for the first reservation and the reservation updates as well. | getRequestedValidityDate(): ?\DateTime | setRequestedValidityDate(?\DateTime requestedValidityDate): void |
| `cardAcquisitionReference` | [`?TransactionIDType`](../../doc/models/transaction-id-type.md) | Optional | Identification of a transaction for the Sale System or the POI System. | getCardAcquisitionReference(): ?TransactionIDType | setCardAcquisitionReference(?TransactionIDType cardAcquisitionReference): void |
| `instalment` | [`?Instalment1`](../../doc/models/instalment-1.md) | Optional | Information related an instalment transaction. To request an instalment to the issuer, or to make individual instalments of a payment transaction. | getInstalment(): ?Instalment1 | setInstalment(?Instalment1 instalment): void |
| `paymentInstrumentData` | [`?PaymentInstrumentData`](../../doc/models/payment-instrument-data.md) | Optional | Data related to the instrument of payment for the transaction.<br>Sent in the result of the payment transaction. For a card, it could also be sent in the `CardAcquisition` response, to be processed by the Sale System. | getPaymentInstrumentData(): ?PaymentInstrumentData | setPaymentInstrumentData(?PaymentInstrumentData paymentInstrumentData): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentData1Builder;
use AdyenLib\Models\PaymentType1Enum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\TransactionIDTypeBuilder;
use AdyenLib\Models\Builders\Instalment1Builder;
use AdyenLib\Models\InstalmentTypeEnum;
use AdyenLib\Models\PeriodUnit1Enum;

$paymentData1 = PaymentData1Builder::init()
    ->paymentType(PaymentType1Enum::ONETIMERESERVATION)
    ->splitPaymentFlag(false)
    ->requestedValidityDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
    ->cardAcquisitionReference(
        TransactionIDTypeBuilder::init(
            'TransactionID8',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
    ->instalment(
        Instalment1Builder::init()
            ->instalmentType(InstalmentTypeEnum::DEFERREDINSTALMENTS)
            ->sequenceNumber(106)
            ->planID('PlanID4')
            ->period(70)
            ->periodUnit(PeriodUnit1Enum::MONTHLY)
            ->build()
    )
    ->build();
```

