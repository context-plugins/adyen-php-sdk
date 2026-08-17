
# Grant Offer

## Structure

`GrantOffer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The identifier of the account holder to which the grant is offered. | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |
| `amount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The principal amount of the grant. | getAmount(): ?Amount17 | setAmount(?Amount17 amount): void |
| `contractType` | [`?string(ContractTypeEnum)`](../../doc/models/contract-type-enum.md) | Optional | The contract type of the grant offer. Possible value: **cashAdvance**, **loan**. | getContractType(): ?string | setContractType(?string contractType): void |
| `expiresAt` | `?DateTime` | Optional | The end date of the grant offer validity period. | getExpiresAt(): ?\DateTime | setExpiresAt(?\DateTime expiresAt): void |
| `fee` | [`?Fee1`](../../doc/models/fee-1.md) | Optional | Details of the fee configuration. | getFee(): ?Fee1 | setFee(?Fee1 fee): void |
| `id` | `?string` | Optional | The unique identifier of the grant offer. | getId(): ?string | setId(?string id): void |
| `repayment` | [`?Repayment2`](../../doc/models/repayment-2.md) | Optional | Details of the repayment configuration. | getRepayment(): ?Repayment2 | setRepayment(?Repayment2 repayment): void |
| `startsAt` | `?DateTime` | Optional | The starting date of the grant offer validity period. | getStartsAt(): ?\DateTime | setStartsAt(?\DateTime startsAt): void |

## Example

```php
use AdyenLib\Models\Builders\GrantOfferBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\ContractTypeEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\Fee1Builder;

$grantOffer = GrantOfferBuilder::init(
    'accountHolderId4'
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
        Fee1Builder::init(
            Amount17Builder::init(
                'currency2',
                110
            )->build()
        )->build()
    )
    ->id('id2')
    ->build();
```

