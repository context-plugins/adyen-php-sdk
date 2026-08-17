
# Update Account Holder State Request

## Structure

`UpdateAccountHolderStateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The code of the Account Holder on which to update the state. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `disable` | `bool` | Required | If true, disable the requested state.  If false, enable the requested state. | getDisable(): bool | setDisable(bool disable): void |
| `reason` | `?string` | Optional | The reason that the state is being updated.<br><br>> Required if the state is being disabled. | getReason(): ?string | setReason(?string reason): void |
| `stateType` | [`string(StateTypeEnum)`](../../doc/models/state-type-enum.md) | Required | The state to be updated.<br><br>> Permitted values are: `Processing`, `Payout` | getStateType(): string | setStateType(string stateType): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateAccountHolderStateRequestBuilder;
use AdyenLib\Models\StateTypeEnum;

$updateAccountHolderStateRequest = UpdateAccountHolderStateRequestBuilder::init(
    'accountHolderCode6',
    false,
    StateTypeEnum::PAYOUT
)
    ->reason('reason6')
    ->build();
```

