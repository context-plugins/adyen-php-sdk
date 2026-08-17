
# Authentication Response Enum

In 3D Secure 2, this is the `transStatus` from the challenge result. If the transaction was frictionless, omit this parameter.

## Enumeration

`AuthenticationResponseEnum`

## Fields

| Name |
|  --- |
| `Y` |
| `N` |
| `U` |
| `A` |

## Example

```php
use AdyenLib\Models\AuthenticationResponseEnum;

$authenticationResponse = AuthenticationResponseEnum::U;
```

