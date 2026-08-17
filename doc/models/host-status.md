
# Host Status

Indicate the reachability of the host by the POI Terminal.
State of a Host.

## Structure

`HostStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acquirerID` | `int` | Required | Identification of the Acquirer. | getAcquirerID(): int | setAcquirerID(int acquirerID): void |
| `isReachableFlag` | `?bool` | Optional | Indicate if a Host is reachable.<br><br>**Default**: `true` | getIsReachableFlag(): ?bool | setIsReachableFlag(?bool isReachableFlag): void |

## Example

```php
use AdyenLib\Models\Builders\HostStatusBuilder;

$hostStatus = HostStatusBuilder::init(
    230
)
    ->isReachableFlag(true)
    ->build();
```

