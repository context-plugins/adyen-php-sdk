
# Dynamic Offer

## Structure

`DynamicOffer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier of the account holder that the dynamic offer is for. | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |
| `contractType` | [`string(ContractTypeEnum)`](../../doc/models/contract-type-enum.md) | Required | The contract type of the offer.<br><br>Possible values:<br><br>* **loan**<br>* **cashAdvance** | getContractType(): string | setContractType(string contractType): void |
| `expiresAt` | `DateTime` | Required | The expiration date and time of the offer validity period. | getExpiresAt(): \DateTime | setExpiresAt(\DateTime expiresAt): void |
| `financingType` | [`string(FinancingType2Enum)`](../../doc/models/financing-type-2-enum.md) | Required | The type of financing that the offer is for.<br><br>Possible values: **businessFinancing**. | getFinancingType(): string | setFinancingType(string financingType): void |
| `id` | `string` | Required | The unique identifier of the dynamic offer. | getId(): string | setId(string id): void |
| `maximumAmount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The maximum financing amount available to the account holder under this offer. | getMaximumAmount(): Amount17 | setMaximumAmount(Amount17 maximumAmount): void |
| `minimumAmount` | [`Amount17`](../../doc/models/amount-17.md) | Required | The minimum financing amount available to the account holder under this offer. | getMinimumAmount(): Amount17 | setMinimumAmount(Amount17 minimumAmount): void |
| `repayment` | [`DynamicOfferRepayment2`](../../doc/models/dynamic-offer-repayment-2.md) | Required | Contains information about the repayment configuration of the grant. | getRepayment(): DynamicOfferRepayment2 | setRepayment(DynamicOfferRepayment2 repayment): void |
| `startsAt` | `DateTime` | Required | The starting date and time of the offer validity period. | getStartsAt(): \DateTime | setStartsAt(\DateTime startsAt): void |

## Example

```php
use AdyenLib\Models\Builders\DynamicOfferBuilder;
use AdyenLib\Models\ContractTypeEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\FinancingType2Enum;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\DynamicOfferRepayment2Builder;
use AdyenLib\Models\Builders\RepaymentTermBuilder;

$dynamicOffer = DynamicOfferBuilder::init(
    'accountHolderId6',
    ContractTypeEnum::CASHADVANCE,
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    FinancingType2Enum::HARDWAREFINANCING,
    'id2',
    Amount17Builder::init(
        'currency0',
        190
    )->build(),
    Amount17Builder::init(
        'currency2',
        96
    )->build(),
    DynamicOfferRepayment2Builder::init(
        RepaymentTermBuilder::init(
            248
        )
            ->maximumDays(24)
            ->build()
    )->build(),
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
)->build();
```

