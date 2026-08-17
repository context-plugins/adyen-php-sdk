
# Response 11

Result of a message request processing.

## Structure

`Response11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `result` | [`string(Result11Enum)`](../../doc/models/result-11-enum.md) | Required | Result of the processing of the message.<br>Possible values:<br><br>* **Failure**<br>* **Partial**<br>* **Success** | getResult(): string | setResult(string result): void |
| `errorCondition` | [`?string(ErrorCondition1Enum)`](../../doc/models/error-condition-1-enum.md) | Optional | Condition that has produced an error on the processing of a message request.<br>Returned if Result is not Success.<br>Possible values:<br><br>* **Aborted**<br>* **Busy**<br>* **Cancel**<br>* **DeviceOut**<br>* **InProgress**<br>* **InsertedCard**<br>* **InvalidCard**<br>* **LoggedOut**<br>* **MessageFormat**<br>* **NotAllowed**<br>* **NotFound**<br>* **PaymentRestriction**<br>* **Refusal**<br>* **UnavailableDevice**<br>* **UnavailableService**<br>* **UnreachableHost**<br>* **WrongPIN** | getErrorCondition(): ?string | setErrorCondition(?string errorCondition): void |
| `additionalResponse` | `?string` | Optional | Additional information related to processing status of a message request.<br>If present, the POI logs it for further examination.<br><br>**Constraints**: *Pattern*: `^.+$` | getAdditionalResponse(): ?string | setAdditionalResponse(?string additionalResponse): void |

## Example

```php
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;

$response11 = Response11Builder::init(
    Result11Enum::PARTIAL
)
    ->errorCondition(ErrorCondition1Enum::UNREACHABLEHOST)
    ->additionalResponse('AdditionalResponse4')
    ->build();
```

