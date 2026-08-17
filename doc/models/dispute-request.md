
# Dispute Request

## Structure

`DisputeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Your description for the dispute.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `50` | getDescription(): ?string | setDescription(?string description): void |
| `disputedAmount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The amount for which you dispute the transaction. The disputed amount cannot be greater than the transaction amount. If you do not provide an amount, the entire transaction amount will be disputed. | getDisputedAmount(): ?Amount17 | setDisputedAmount(?Amount17 disputedAmount): void |
| `duplicateInfo` | [`?DuplicateInfo1`](../../doc/models/duplicate-info-1.md) | Optional | Additional information for raising a dispute of `type` **duplicate**. Required for disputes of `type` **duplicate**. | getDuplicateInfo(): ?DuplicateInfo1 | setDuplicateInfo(?DuplicateInfo1 duplicateInfo): void |
| `fraudInfo` | [`?FraudInfo1`](../../doc/models/fraud-info-1.md) | Optional | Additional information for raising a dispute of `type` **fraud**. Required for disputes of `type` **fraud**. | getFraudInfo(): ?FraudInfo1 | setFraudInfo(?FraudInfo1 fraudInfo): void |
| `notDeliveredInfo` | [`?NotDeliveredInfo1`](../../doc/models/not-delivered-info-1.md) | Optional | Additional information for raising a dispute of `type` **notDelivered**. Required for disputes of `type` **notDelivered**. | getNotDeliveredInfo(): ?NotDeliveredInfo1 | setNotDeliveredInfo(?NotDeliveredInfo1 notDeliveredInfo): void |
| `otherInfo` | [`?OtherInfo3`](../../doc/models/other-info-3.md) | Optional | Additional information for raising a dispute of `type` **other**. Required for disputes of `type` **other**.<br><br>**Note:** The **other** dispute `type` is currently in beta testing. Do not create or submit any disputes for this dispute `type` at this time. | getOtherInfo(): ?OtherInfo3 | setOtherInfo(?OtherInfo3 otherInfo): void |
| `status` | [`?string(DisputeStatus1Enum)`](../../doc/models/dispute-status-1-enum.md) | Optional | The current status of the dispute.<br><br>When you create a dispute, you can only set the `status` to **draft**. When you update a dispute, you can set the `status` to **submitted** or **closed**.<br><br>Possible values: **draft**, **submitted**, **closed**, **won**, **chargeback**, **secondPresentment**. | getStatus(): ?string | setStatus(?string status): void |
| `transactionId` | `string` | Required | The unique reference of the transaction for which you are raising the dispute.<br><br>**Constraints**: *Minimum Length*: `1` | getTransactionId(): string | setTransactionId(string transactionId): void |
| `type` | `string` | Required | The type of the dispute.<br><br>Possible values: **duplicate**, **fraud**, **notDelivered**, **other**.<br><br>**Note:** The **other** dispute `type` is currently in beta testing. Do not create or submit any disputes for this dispute `type` at this time. | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\DisputeRequestBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\DuplicateInfo1Builder;
use AdyenLib\Models\Builders\FraudInfo1Builder;
use AdyenLib\Models\Builders\NotDeliveredInfo1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\ProductType21Enum;

$disputeRequest = DisputeRequestBuilder::init(
    'transactionId2',
    'type2'
)
    ->description('description2')
    ->disputedAmount(
        Amount17Builder::init(
            'currency0',
            162
        )->build()
    )
    ->duplicateInfo(
        DuplicateInfo1Builder::init(
            'duplicateTransactionId4',
            false
        )
            ->sameIssuer(false)
            ->build()
    )
    ->fraudInfo(
        FraudInfo1Builder::init(
            false,
            false,
            'descriptionOfIssue2'
        )
            ->reportOnly(false)
            ->build()
    )
    ->notDeliveredInfo(
        NotDeliveredInfo1Builder::init(
            'descriptionOfIssue6',
            DateTimeHelper::fromSimpleDateRequired('2016-03-13'),
            ProductType21Enum::GOODS
        )
            ->agreedDeliveryLocation('agreedDeliveryLocation4')
            ->dateOfCancellation(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->deliveredToWrongLocation(false)
            ->didCardholderReturn(false)
            ->isDeliveryLate(false)
            ->build()
    )
    ->build();
```

