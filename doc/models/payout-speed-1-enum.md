
# Payout Speed 1 Enum

Speed at which payouts for this account are processed.

Possible values: `STANDARD` (default), `SAME_DAY`.

## Enumeration

`PayoutSpeed1Enum`

## Fields

| Name |
|  --- |
| `INSTANT` |
| `SAME_DAY` |
| `STANDARD` |

## Example

```php
use AdyenLib\Models\PayoutSpeed1Enum;

$payoutSpeed1 = PayoutSpeed1Enum::INSTANT;
```

