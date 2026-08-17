
# Grant Offer 1

## Structure

`GrantOffer1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier of the account holder to which the grant is offered. | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |
| `amount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The amount that would be paid out to the user for business financing. | getAmount(): ?Amount17 | setAmount(?Amount17 amount): void |
| `contractType` | [`?string(ContractTypeEnum)`](../../doc/models/contract-type-enum.md) | Optional | The contract type of the offer.<br><br>Possible values:<br><br>* **loan**<br>* **cashAdvance** | getContractType(): ?string | setContractType(?string contractType): void |
| `expiresAt` | `?DateTime` | Optional | The expiration date and time of the offer validity period. | getExpiresAt(): ?\DateTime | setExpiresAt(?\DateTime expiresAt): void |
| `fee` | [`?GrantOfferFee1`](../../doc/models/grant-offer-fee-1.md) | Optional | Contains information about the fee that your user would pay for the grant. | getFee(): ?GrantOfferFee1 | setFee(?GrantOfferFee1 fee): void |
| `id` | `?string` | Optional | The unique identifier of the offer. | getId(): ?string | setId(?string id): void |
| `repayment` | [`?Repayment11`](../../doc/models/repayment-11.md) | Optional | Contains information about the repayment configuration of the grant. | getRepayment(): ?Repayment11 | setRepayment(?Repayment11 repayment): void |
| `startsAt` | `?DateTime` | Optional | The starting date and time of the offer validity period. | getStartsAt(): ?\DateTime | setStartsAt(?\DateTime startsAt): void |

## Example

```php
use AdyenLib\Models\Builders\GrantOffer1Builder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\ContractTypeEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\GrantOfferFee1Builder;

$grantOffer1 = GrantOffer1Builder::init(
    'accountHolderId0'
)
    ->amount(
        Amount17Builder::init(
            'currency2',
            110
        )->build()
    )
    ->contractType(ContractTypeEnum::CASHADVANCE)
    ->expiresAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->fee(
        GrantOfferFee1Builder::init(
            Amount17Builder::init(
                'currency2',
                110
            )->build()
        )
            ->aprBasisPoints(142)
            ->build()
    )
    ->id('id8')
    ->build();
```

