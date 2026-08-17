
# Response 1

Result of a message request processing.
If Result is Success, `ErrorCondition` is absent or not used in the processing of the message. In the other cases, the `ErrorCondition` has to be present and can refine the processing of the message response. `AdditionalResponse` gives more information about the success or the failure of the message request processing, for logging without real time involvements.

## Structure

`Response1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `result` | [`string(Result11Enum)`](../../doc/models/result-11-enum.md) | Required | Result of the processing of the message.<br>Possible values:<br><br>* **Failure**<br>* **Partial**<br>* **Success** | getResult(): string | setResult(string result): void |
| `errorCondition` | [`?string(ErrorCondition1Enum)`](../../doc/models/error-condition-1-enum.md) | Optional | Condition that has produced an error on the processing of a message request.<br>Returned if Result is not Success.<br>Possible values:<br><br>* **Aborted**<br>* **Busy**<br>* **Cancel**<br>* **DeviceOut**<br>* **InProgress**<br>* **InsertedCard**<br>* **InvalidCard**<br>* **LoggedOut**<br>* **MessageFormat**<br>* **NotAllowed**<br>* **NotFound**<br>* **PaymentRestriction**<br>* **Refusal**<br>* **UnavailableDevice**<br>* **UnavailableService**<br>* **UnreachableHost**<br>* **WrongPIN** | getErrorCondition(): ?string | setErrorCondition(?string errorCondition): void |
| `additionalResponse` | `?string` | Optional | Additional information related to processing status of a message request.<br>If present, the POI logs it for further examination.<br><br>**Constraints**: *Pattern*: `^.+$` | getAdditionalResponse(): ?string | setAdditionalResponse(?string additionalResponse): void |

## Example

```php
use AdyenLib\Models\Builders\Response1Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;

$response1 = Response1Builder::init(
    Result11Enum::FAILURE
)
    ->errorCondition(ErrorCondition1Enum::CANCEL)
    ->additionalResponse('AdditionalResponse4')
    ->build();
```

