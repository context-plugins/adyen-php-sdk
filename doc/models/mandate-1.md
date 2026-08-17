
# Mandate 1

## Structure

`Mandate1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccountId` | `?string` | Optional | The unique identifier of the balance account linked to the payment instrument. | getBalanceAccountId(): ?string | setBalanceAccountId(?string balanceAccountId): void |
| `counterparty` | [`?MandateBankAccount2`](../../doc/models/mandate-bank-account-2.md) | Optional | Contains information to identify the counterparty. | getCounterparty(): ?MandateBankAccount2 | setCounterparty(?MandateBankAccount2 counterparty): void |
| `createdAt` | `?DateTime` | Optional | The date when the mandate was created. | getCreatedAt(): ?\DateTime | setCreatedAt(?\DateTime createdAt): void |
| `id` | `?string` | Optional | The unique identifier of the mandate. | getId(): ?string | setId(?string id): void |
| `paymentInstrumentId` | `?string` | Optional | The unique identifier of the payment instrument linked to the mandate. | getPaymentInstrumentId(): ?string | setPaymentInstrumentId(?string paymentInstrumentId): void |
| `status` | [`?string(MandateStatus2Enum)`](../../doc/models/mandate-status-2-enum.md) | Optional | The status of the mandate.<br><br>Possible values: **pending**, **approved**, **cancelled**. | getStatus(): ?string | setStatus(?string status): void |
| `type` | [`?string(MandateType2Enum)`](../../doc/models/mandate-type-2-enum.md) | Optional | The type of mandate. Possible value: **bacs**. | getType(): ?string | setType(?string type): void |
| `updatedAt` | `?DateTime` | Optional | The date when the mandate was updated. | getUpdatedAt(): ?\DateTime | setUpdatedAt(?\DateTime updatedAt): void |

## Example

```php
use AdyenLib\Models\Builders\Mandate1Builder;
use AdyenLib\Models\Builders\MandateBankAccount2Builder;
use AdyenLib\Models\Builders\MandatePartyIdentification2Builder;
use AdyenLib\Models\Builders\MandateAccountIdentification2Builder;
use AdyenLib\Utils\DateTimeHelper;

$mandate1 = Mandate1Builder::init()
    ->balanceAccountId('balanceAccountId0')
    ->counterparty(
        MandateBankAccount2Builder::init(
            MandatePartyIdentification2Builder::init()
                ->fullName('fullName0')
                ->build(),
            MandateAccountIdentification2Builder::init()
                ->type('MandateAccountIdentification2')
                ->build()
        )->build()
    )
    ->createdAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->id('id8')
    ->paymentInstrumentId('paymentInstrumentId0')
    ->build();
```

