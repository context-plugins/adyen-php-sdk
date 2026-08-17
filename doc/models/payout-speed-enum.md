
# Payout Speed Enum

Speed with which payouts for this account are processed. Permitted values: `STANDARD`, `SAME_DAY`.

## Enumeration

`PayoutSpeedEnum`

## Fields

| Name |
|  --- |
| `INSTANT` |
| `SAME_DAY` |
| `STANDARD` |

## Example

```php
use AdyenLib\Models\PayoutSpeedEnum;

$payoutSpeed = PayoutSpeedEnum::SAME_DAY;
```

