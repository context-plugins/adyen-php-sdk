
# List External Terminal Actions Response

## Structure

`ListExternalTerminalActionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(ExternalTerminalAction[])`](../../doc/models/external-terminal-action.md) | Optional | The list of terminal actions. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\ListExternalTerminalActionsResponseBuilder;
use AdyenLib\Models\Builders\ExternalTerminalActionBuilder;
use AdyenLib\Utils\DateTimeHelper;

$listExternalTerminalActionsResponse = ListExternalTerminalActionsResponseBuilder::init()
    ->data(
        [
            ExternalTerminalActionBuilder::init()
                ->actionType('actionType0')
                ->config('config6')
                ->confirmedAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->id('id0')
                ->result('result4')
                ->build(),
            ExternalTerminalActionBuilder::init()
                ->actionType('actionType0')
                ->config('config6')
                ->confirmedAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->id('id0')
                ->result('result4')
                ->build()
        ]
    )
    ->build();
```

