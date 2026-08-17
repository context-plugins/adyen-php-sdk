
# Fraud Info

## Structure

`FraudInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardDoesNotBelongToCardholder` | `bool` | Required | The card is no longer in the cardholder's possession. Set to **true** if the card is lost or stolen. | getCardDoesNotBelongToCardholder(): bool | setCardDoesNotBelongToCardholder(bool cardDoesNotBelongToCardholder): void |
| `cardWasCounterfeited` | `bool` | Required | The card was counterfeited. | getCardWasCounterfeited(): bool | setCardWasCounterfeited(bool cardWasCounterfeited): void |
| `descriptionOfIssue` | `string` | Required | Your description of the issue for raising a dispute of `type` **fraud**.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `2500` | getDescriptionOfIssue(): string | setDescriptionOfIssue(string descriptionOfIssue): void |
| `reportOnly` | `?bool` | Optional | Set to **true** to report fraud to Adyen with no further action, such as a request for a chargeback or fee reversal. The default value is **false**. | getReportOnly(): ?bool | setReportOnly(?bool reportOnly): void |

## Example

```php
use AdyenLib\Models\Builders\FraudInfoBuilder;

$fraudInfo = FraudInfoBuilder::init(
    false,
    false,
    'descriptionOfIssue2'
)
    ->reportOnly(false)
    ->build();
```

