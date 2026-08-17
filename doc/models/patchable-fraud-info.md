
# Patchable Fraud Info

## Structure

`PatchableFraudInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardDoesNotBelongToCardholder` | `?bool` | Optional | The card is no longer in the cardholder's possession. Set to **true** if the card is lost or stolen. | getCardDoesNotBelongToCardholder(): ?bool | setCardDoesNotBelongToCardholder(?bool cardDoesNotBelongToCardholder): void |
| `cardWasCounterfeited` | `?bool` | Optional | The card was counterfeited. | getCardWasCounterfeited(): ?bool | setCardWasCounterfeited(?bool cardWasCounterfeited): void |
| `descriptionOfIssue` | `?string` | Optional | Your description of the issue for raising a dispute of `type` **fraud**.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `2500` | getDescriptionOfIssue(): ?string | setDescriptionOfIssue(?string descriptionOfIssue): void |
| `reportOnly` | `?bool` | Optional | Set to **true** to report fraud to Adyen with no further action, such as a request for a chargeback or fee reversal. The default value is **false**. | getReportOnly(): ?bool | setReportOnly(?bool reportOnly): void |

## Example

```php
use AdyenLib\Models\Builders\PatchableFraudInfoBuilder;

$patchableFraudInfo = PatchableFraudInfoBuilder::init()
    ->cardDoesNotBelongToCardholder(false)
    ->cardWasCounterfeited(false)
    ->descriptionOfIssue('descriptionOfIssue4')
    ->reportOnly(false)
    ->build();
```

