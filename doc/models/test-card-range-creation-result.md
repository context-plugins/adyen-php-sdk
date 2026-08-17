
# Test Card Range Creation Result

## Structure

`TestCardRangeCreationResult`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardNumberRangeEnd` | `string` | Required | The last test card number in the generated test card range.<br><br>Example: 5432 1234 1234 4321 | getCardNumberRangeEnd(): string | setCardNumberRangeEnd(string cardNumberRangeEnd): void |
| `cardNumberRangeStart` | `string` | Required | The first test card number in the generated test card range.<br><br>Example: 5432 1234 1234 1234 | getCardNumberRangeStart(): string | setCardNumberRangeStart(string cardNumberRangeStart): void |
| `creationResultCode` | [`string(CreationResultCodeEnum)`](../../doc/models/creation-result-code-enum.md) | Required | Notification message. It informs about the outcome of the operation. Possible values:<br><br>* CREATED<br>* ALREADY_EXISTS<br>* ERROR | getCreationResultCode(): string | setCreationResultCode(string creationResultCode): void |
| `message` | `?string` | Optional | An optional information message about the result. | getMessage(): ?string | setMessage(?string message): void |

## Example

```php
use AdyenLib\Models\Builders\TestCardRangeCreationResultBuilder;
use AdyenLib\Models\CreationResultCodeEnum;

$testCardRangeCreationResult = TestCardRangeCreationResultBuilder::init(
    'cardNumberRangeEnd6',
    'cardNumberRangeStart8',
    CreationResultCodeEnum::ERROR
)
    ->message('message0')
    ->build();
```

