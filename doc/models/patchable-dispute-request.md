
# Patchable Dispute Request

## Structure

`PatchableDisputeRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `duplicateInfo` | [PatchableDuplicateInfo](../../doc/models/patchable-duplicate-info.md)\|null | Optional | This is a container for one-of cases. | getDuplicateInfo(): ?PatchableDuplicateInfo | setDuplicateInfo(?PatchableDuplicateInfo duplicateInfo): void |
| `fraudInfo` | [PatchableFraudInfo](../../doc/models/patchable-fraud-info.md)\|null | Optional | This is a container for one-of cases. | getFraudInfo(): ?PatchableFraudInfo | setFraudInfo(?PatchableFraudInfo fraudInfo): void |
| `notDeliveredInfo` | [PatchableNotDeliveredInfo](../../doc/models/patchable-not-delivered-info.md)\|null | Optional | This is a container for one-of cases. | getNotDeliveredInfo(): ?PatchableNotDeliveredInfo | setNotDeliveredInfo(?PatchableNotDeliveredInfo notDeliveredInfo): void |
| `otherInfo` | [PatchableOtherInfo](../../doc/models/patchable-other-info.md)\|null | Optional | This is a container for one-of cases. | getOtherInfo(): ?PatchableOtherInfo | setOtherInfo(?PatchableOtherInfo otherInfo): void |
| `status` | string([DisputeStatusEnum](../../doc/models/dispute-status-enum.md))\|null | Optional | This is a container for one-of cases. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableDisputeRequestBuilder;
use AdyenLib\Models\Builders\PatchableDuplicateInfoBuilder;
use AdyenLib\Models\Builders\PatchableFraudInfoBuilder;
use AdyenLib\Models\Builders\PatchableNotDeliveredInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\PatchableOtherInfoBuilder;
use AdyenLib\Models\SubType11Enum;
use AdyenLib\Models\ProductType11Enum;
use AdyenLib\Models\DisputeStatusEnum;

$patchableDisputeRequest = PatchableDisputeRequestBuilder::init()
    ->duplicateInfo(
        PatchableDuplicateInfoBuilder::init()
            ->duplicateTransactionId('duplicateTransactionId6')
            ->sameCard(false)
            ->sameIssuer(false)
            ->build()
    )
    ->fraudInfo(
        PatchableFraudInfoBuilder::init()
            ->cardDoesNotBelongToCardholder(false)
            ->cardWasCounterfeited(false)
            ->descriptionOfIssue('descriptionOfIssue6')
            ->reportOnly(false)
            ->build()
    )
    ->notDeliveredInfo(
        PatchableNotDeliveredInfoBuilder::init()
            ->agreedDeliveryLocation('agreedDeliveryLocation2')
            ->dateOfCancellation(DateTimeHelper::fromSimpleDate('2016-03-13'))
            ->deliveredToWrongLocation(false)
            ->descriptionOfIssue('descriptionOfIssue2')
            ->didCardholderReturn(false)
            ->build()
    )
    ->otherInfo(
        PatchableOtherInfoBuilder::init()
            ->descriptionOfIssue('descriptionOfIssue6')
            ->subType(SubType11Enum::COUNTERFEIT)
            ->whatWasPurchased(ProductType11Enum::GOODS)
            ->build()
    )
    ->status(
        DisputeStatusEnum::SECONDPRESENTMENT
    )
    ->build();
```

