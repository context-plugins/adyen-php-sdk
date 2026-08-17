
# Platform Chargeback Logic 4

Dictates the behavior of how a potential chargeback should be booked when using Adyen Platforms.

## Structure

`PlatformChargebackLogic4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `behavior` | [`?string(BehaviorEnum)`](../../doc/models/behavior-enum.md) | Optional | The method of handling the chargeback.<br><br>Possible values: **deductFromLiableAccount**, **deductFromOneBalanceAccount**, **deductAccordingToSplitRatio**. | getBehavior(): ?string | setBehavior(?string behavior): void |
| `costAllocationAccount` | `?string` | Optional | The unique identifier of the balance account to which the chargeback fees are booked. By default, the chargeback fees are booked to your liable balance account. | getCostAllocationAccount(): ?string | setCostAllocationAccount(?string costAllocationAccount): void |
| `targetAccount` | `?string` | Optional | The unique identifier of the balance account against which the disputed amount is booked.<br><br>Required if `behavior` is **deductFromOneBalanceAccount**. | getTargetAccount(): ?string | setTargetAccount(?string targetAccount): void |

## Example

```php
use AdyenLib\Models\Builders\PlatformChargebackLogic4Builder;
use AdyenLib\Models\BehaviorEnum;

$platformChargebackLogic4 = PlatformChargebackLogic4Builder::init()
    ->behavior(BehaviorEnum::DEDUCTFROMONEBALANCEACCOUNT)
    ->costAllocationAccount('costAllocationAccount0')
    ->targetAccount('targetAccount8')
    ->build();
```

