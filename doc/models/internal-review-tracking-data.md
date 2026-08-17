
# Internal Review Tracking Data

## Structure

`InternalReviewTrackingData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | [`?string(Reason11Enum)`](../../doc/models/reason-11-enum.md) | Optional | The reason why the transfer failed Adyen's internal review.<br><br>Possible values:<br><br>- **refusedForRegulatoryReasons**: the transfer does not comply with Adyen's risk policy. For more information, [contact the Support Team](https://www.adyen.help/hc/en-us/requests/new). | getReason(): ?string | setReason(?string reason): void |
| `status` | [`string(Status44Enum)`](../../doc/models/status-44-enum.md) | Required | The status of the transfer.<br><br>Possible values:<br><br>- **pending**: the transfer is under internal review by Adyen.<br><br>- **failed**: the transfer failed Adyen's internal review. For details, see `reason`. | getStatus(): string | setStatus(string status): void |
| `type` | `string` | Required, Constant | The type of tracking event.<br><br>Possible values:<br><br>- **internalReview**: the transfer was flagged because it does not comply with Adyen's risk policy.<br><br>**Value**: `'internalReview'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\InternalReviewTrackingDataBuilder;
use AdyenLib\Models\Status44Enum;
use AdyenLib\Models\Reason11Enum;

$internalReviewTrackingData = InternalReviewTrackingDataBuilder::init(
    Status44Enum::PENDING
)
    ->reason(Reason11Enum::REFUSEDFORREGULATORYREASONS)
    ->build();
```

