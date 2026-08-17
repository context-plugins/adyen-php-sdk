
# Transfer Event

## Structure

`TransferEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The original journal amount. Only applicable for [issuing](https://docs.adyen.com/issuing/) integrations. | getAmount(): ?Amount17 | setAmount(?Amount17 amount): void |
| `amountAdjustments` | [`?(AmountAdjustment[])`](../../doc/models/amount-adjustment.md) | Optional | The amount adjustments in this transfer. Only applicable for [issuing](https://docs.adyen.com/issuing/) integrations. | getAmountAdjustments(): ?array | setAmountAdjustments(?array amountAdjustments): void |
| `arn` | `?string` | Optional | Scheme unique arn identifier useful for tracing captures, chargebacks, refunds, etc. | getArn(): ?string | setArn(?string arn): void |
| `bookingDate` | `?DateTime` | Optional | The date when the transfer request was sent. | getBookingDate(): ?\DateTime | setBookingDate(?\DateTime bookingDate): void |
| `estimatedArrivalTime` | `?DateTime` | Optional | The estimated time when the beneficiary should have access to the funds. | getEstimatedArrivalTime(): ?\DateTime | setEstimatedArrivalTime(?\DateTime estimatedArrivalTime): void |
| `eventsData` | array<[InterchangeData](../../doc/models/interchange-data.md)\|[IssuingTransactionData](../../doc/models/issuing-transaction-data.md)\|[MerchantPurchaseData](../../doc/models/merchant-purchase-data.md)>\|null | Optional | This is Array of a container for one-of cases. | getEventsData(): ?array | setEventsData(?array eventsData): void |
| `externalReason` | [`?ExternalReason1`](../../doc/models/external-reason-1.md) | Optional | The external reason for the transfer status. | getExternalReason(): ?ExternalReason1 | setExternalReason(?ExternalReason1 externalReason): void |
| `id` | `?string` | Optional | The unique identifier of the transfer event. | getId(): ?string | setId(?string id): void |
| `modification` | [`?Modification2`](../../doc/models/modification-2.md) | Optional | The payment modification. Only applicable for [returned internal transfers](https://docs.adyen.com/platforms/internal-fund-transfers/internal-transfer-webhooks/#returned-internal-transfer). | getModification(): ?Modification2 | setModification(?Modification2 modification): void |
| `mutations` | [`?(BalanceMutation[])`](../../doc/models/balance-mutation.md) | Optional | The list of balance mutations per event. | getMutations(): ?array | setMutations(?array mutations): void |
| `originalAmount` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | The amount in the original currency. Only applicable for [issuing](https://docs.adyen.com/issuing/) integrations. | getOriginalAmount(): ?Amount17 | setOriginalAmount(?Amount17 originalAmount): void |
| `reason` | [`?string(Reason1Enum)`](../../doc/models/reason-1-enum.md) | Optional | The reason for the transfer status. | getReason(): ?string | setReason(?string reason): void |
| `status` | [`?string(Status24Enum)`](../../doc/models/status-24-enum.md) | Optional | The status of the transfer event. | getStatus(): ?string | setStatus(?string status): void |
| `tracingData` | [UKFpsTracingData](../../doc/models/uk-fps-tracing-data.md)\|[USAchTracingData](../../doc/models/us-ach-tracing-data.md)\|null | Optional | This is a container for one-of cases. | getTracingData(): | setTracingData( tracingData): void |
| `trackingData` | [ConfirmationTrackingData](../../doc/models/confirmation-tracking-data.md)\|[EstimationTrackingData](../../doc/models/estimation-tracking-data.md)\|[InternalReviewTrackingData](../../doc/models/internal-review-tracking-data.md)\|null | Optional | This is a container for one-of cases. | getTrackingData(): | setTrackingData( trackingData): void |
| `transactionId` | `?string` | Optional | The id of the transaction that is related to this accounting event. Only sent for events of type **accounting** where the balance changes. | getTransactionId(): ?string | setTransactionId(?string transactionId): void |
| `type` | [`?string(Type73Enum)`](../../doc/models/type-73-enum.md) | Optional | The type of the transfer event. Possible values: **accounting**, **tracking**. | getType(): ?string | setType(?string type): void |
| `updateDate` | `?DateTime` | Optional | The date when the tracking status was updated. | getUpdateDate(): ?\DateTime | setUpdateDate(?\DateTime updateDate): void |
| `valueDate` | `?DateTime` | Optional | The date when the funds are expected to be deducted from or credited to the balance account. This date can be in either the past or future. | getValueDate(): ?\DateTime | setValueDate(?\DateTime valueDate): void |

## Example

```php
use AdyenLib\Models\Builders\TransferEventBuilder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\Builders\AmountAdjustmentBuilder;
use AdyenLib\Models\AmountAdjustmentTypeEnum;
use AdyenLib\Utils\DateTimeHelper;

$transferEvent = TransferEventBuilder::init()
    ->amount(
        Amount17Builder::init(
            'currency2',
            110
        )->build()
    )
    ->amountAdjustments(
        [
            AmountAdjustmentBuilder::init()
                ->amount(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )
                ->amountAdjustmentType(AmountAdjustmentTypeEnum::ATMMARKUP)
                ->basepoints(170)
                ->build(),
            AmountAdjustmentBuilder::init()
                ->amount(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )
                ->amountAdjustmentType(AmountAdjustmentTypeEnum::ATMMARKUP)
                ->basepoints(170)
                ->build(),
            AmountAdjustmentBuilder::init()
                ->amount(
                    Amount17Builder::init(
                        'currency2',
                        110
                    )->build()
                )
                ->amountAdjustmentType(AmountAdjustmentTypeEnum::ATMMARKUP)
                ->basepoints(170)
                ->build()
        ]
    )
    ->arn('arn8')
    ->bookingDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->estimatedArrivalTime(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

