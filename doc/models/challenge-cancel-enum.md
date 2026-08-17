
# Challenge Cancel Enum

Indicator informing the Access Control Server (ACS) and the Directory Server (DS) that the authentication has been cancelled. For possible values, refer to [3D Secure API reference](https://docs.adyen.com/online-payments/3d-secure/api-reference#mpidata).

## Enumeration

`ChallengeCancelEnum`

## Fields

| Name |
|  --- |
| `ENUM_01` |
| `ENUM_02` |
| `ENUM_03` |
| `ENUM_04` |
| `ENUM_05` |
| `ENUM_06` |
| `ENUM_07` |

## Example

```php
use AdyenLib\Models\ChallengeCancelEnum;

$challengeCancel = ChallengeCancelEnum::ENUM_06;
```

