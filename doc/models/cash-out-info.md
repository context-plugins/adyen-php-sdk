
# Cash Out Info

## Structure

`CashOutInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | Contains the amount of the cashout, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `counterparty` | [`?CashOutInfoCounterparty1`](../../doc/models/cash-out-info-counterparty-1.md) | Optional | Contains information about the counterparty of the cashout transfer. | getCounterparty(): ?CashOutInfoCounterparty1 | setCounterparty(?CashOutInfoCounterparty1 counterparty): void |
| `description` | `?string` | Optional | Allowed and returned only when you provide the `counterparty.transferInstrumentId` field.<br><br>Your description of the cashout transfer. This description is used by most banks as the transfer description. We recommend sending a maximum of 140 characters, otherwise the description may be truncated.<br><br>If you do not provide a description, Adyen generates a description automatically. This generated description is not returned in the response.<br><br>Supported characters: **[a-z] [A-Z] [0-9] / - ? : ( ) . , ' + Space**. | getDescription(): ?string | setDescription(?string description): void |
| `fee` | [`?Fee21`](../../doc/models/fee-21.md) | Optional | Contains the currency and value of the cashout fee, in [minor units](https://docs.adyen.com/development-resources/currency-codes). | getFee(): ?Fee21 | setFee(?Fee21 fee): void |
| `id` | `?string` | Optional, Read-only | The ID of the resource. | getId(): ?string | setId(?string id): void |
| `instructingBalanceAccountId` | `string` | Required | The unique identifier of the balance account that initiates the cashout request. | getInstructingBalanceAccountId(): string | setInstructingBalanceAccountId(string instructingBalanceAccountId): void |
| `referenceForBeneficiary` | `?string` | Optional | Allowed and returned only when you provide the `counterparty.transferInstrumentId` field.<br><br>The reference that is sent to the recipient of a cashout transfer. This reference is also sent in all webhooks related to the cashout transfer, so you can use it to track the status of the transfer.<br><br>If you do not provide a reference for the beneficiary, Adyen generates one automatically. This generated reference for the beneficiary is not returned in the response.<br><br>Supported characters: **a-z**, **A-Z**, **0-9**. | getReferenceForBeneficiary(): ?string | setReferenceForBeneficiary(?string referenceForBeneficiary): void |
| `transferInstrumentId` | `?string` | Optional | **Use `counterparty.transferInstrumentId` instead.**<br><br>The unique identifier of the counterparty transfer instrument. | getTransferInstrumentId(): ?string | setTransferInstrumentId(?string transferInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\CashOutInfoBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\CashOutInfoCounterparty1Builder;
use AdyenLib\Models\Builders\Fee21Builder;

$cashOutInfo = CashOutInfoBuilder::init(
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    'instructingBalanceAccountId2'
)
    ->counterparty(
        CashOutInfoCounterparty1Builder::init()
            ->transferInstrumentId('transferInstrumentId4')
            ->build()
    )
    ->description('description0')
    ->fee(
        Fee21Builder::init(
            Amount17Builder::init(
                'currency2',
                110
            )->build()
        )->build()
    )
    ->referenceForBeneficiary('referenceForBeneficiary0')
    ->build();
```

