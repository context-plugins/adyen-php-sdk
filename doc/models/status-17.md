
# Status 17

## Structure

`Status17`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actions` | [`?(Action1[])`](../../doc/models/action-1.md) | Optional | A list of actions that need to be completed to proceed with the grant. | getActions(): ?array | setActions(?array actions): void |
| `code` | [`string(CodeEnum)`](../../doc/models/code-enum.md) | Required | The code for the status of the grant. Possible values:<br><br>- **Pending**<br>- **Active**<br>- **Repaid**<br>- **WrittenOff**<br>- **Failed**<br>- **Revoked**<br>- **Requested**<br>- **Reviewing**<br>- **Approved**<br>- **Rejected**<br>- **Cancelled** | getCode(): string | setCode(string code): void |

## Example

```php
use AdyenLib\Models\Builders\Status17Builder;
use AdyenLib\Models\CodeEnum;
use AdyenLib\Models\Builders\Action1Builder;

$status17 = Status17Builder::init(
    CodeEnum::REVOKED
)
    ->actions(
        [
            Action1Builder::init(
                'actionCode6',
                false
            )->build(),
            Action1Builder::init(
                'actionCode6',
                false
            )->build()
        ]
    )->build();
```

