
# Direct Debit Information

## Structure

`DirectDebitInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateOfSignature` | `?DateTime` | Optional | The date when the direct debit mandate was accepted by your user, in [ISO-8601](https://www.w3.org/TR/NOTE-datetime) format. | getDateOfSignature(): ?\DateTime | setDateOfSignature(?\DateTime dateOfSignature): void |
| `dueDate` | `?DateTime` | Optional | The date when the funds are deducted from your user's balance account. | getDueDate(): ?\DateTime | setDueDate(?\DateTime dueDate): void |
| `mandateId` | `?string` | Optional | Your unique identifier for the direct debit mandate. | getMandateId(): ?string | setMandateId(?string mandateId): void |
| `sequenceType` | `?string` | Optional | Identifies the direct debit transfer's type.<br>Possible values: **OneOff**, **First**, **Recurring**, **Final**. | getSequenceType(): ?string | setSequenceType(?string sequenceType): void |

## Example

```php
use AdyenLib\Models\Builders\DirectDebitInformationBuilder;
use AdyenLib\Utils\DateTimeHelper;

$directDebitInformation = DirectDebitInformationBuilder::init()
    ->dateOfSignature(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->dueDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->mandateId('mandateId4')
    ->sequenceType('sequenceType8')
    ->build();
```

