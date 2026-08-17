
# Calculated Grant Offer

## Structure

`CalculatedGrantOffer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier of the account holder that the dynamic offer is for. | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |
| `amount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The financing amount that would be paid out to your user. | getAmount(): Amount17 | setAmount(Amount17 amount): void |
| `contractType` | [`string(ContractTypeEnum)`](../../doc/models/contract-type-enum.md) | Required | The contract type of the offer.<br><br>Possible values:<br><br>* **loan**<br>* **cashAdvance** | getContractType(): string | setContractType(string contractType): void |
| `expiresAt` | `DateTime` | Required | The expiration date and time of the offer validity period. | getExpiresAt(): \DateTime | setExpiresAt(\DateTime expiresAt): void |
| `fee` | [`GrantOfferFee1`](../../doc/models/grant-offer-fee-1.md) | Required | Contains information about the fee that your user would pay for the grant. | getFee(): GrantOfferFee1 | setFee(GrantOfferFee1 fee): void |
| `repayment` | [`Repayment11`](../../doc/models/repayment-11.md) | Required | Contains information about the repayment configuration of the grant. | getRepayment(): Repayment11 | setRepayment(Repayment11 repayment): void |
| `startsAt` | `DateTime` | Required | The starting date and time of the offer validity period. | getStartsAt(): \DateTime | setStartsAt(\DateTime startsAt): void |

## Example

```php
use AdyenLib\Models\Builders\CalculatedGrantOfferBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\ContractTypeEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\GrantOfferFee1Builder;
use AdyenLib\Models\Builders\Repayment11Builder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;
use AdyenLib\Models\Builders\ThresholdRepayment21Builder;

$calculatedGrantOffer = CalculatedGrantOfferBuilder::init(
    'accountHolderId2',
    Amount17Builder::init(
        'currency2',
        110
    )->build(),
    ContractTypeEnum::CASHADVANCE,
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    GrantOfferFee1Builder::init(
        Amount17Builder::init(
            'currency2',
            110
        )->build()
    )
        ->aprBasisPoints(142)
        ->build(),
    Repayment11Builder::init(
        18
    )
        ->term(
            RepaymentTermBuilder::init(
                248
            )
                ->maximumDays(24)
                ->build()
        )
        ->threshold(
            ThresholdRepayment21Builder::init(
                Amount17Builder::init(
                    'currency2',
                    110
                )->build()
            )->build()
        )->build(),
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
)->build();
```

