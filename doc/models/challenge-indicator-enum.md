
# Challenge Indicator Enum

Possibility to specify a preference for receiving a challenge from the issuer.
Allowed values:

* `noPreference`
* `requestNoChallenge`
* `requestChallenge`
* `requestChallengeAsMandate`

## Enumeration

`ChallengeIndicatorEnum`

## Fields

| Name |
|  --- |
| `NOPREFERENCE` |
| `REQUESTNOCHALLENGE` |
| `REQUESTCHALLENGE` |
| `REQUESTCHALLENGEASMANDATE` |

## Example

```php
use AdyenLib\Models\ChallengeIndicatorEnum;

$challengeIndicator = ChallengeIndicatorEnum::REQUESTCHALLENGE;
```

