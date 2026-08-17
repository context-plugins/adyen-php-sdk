
# Verification Status 1 Enum

The status of the verification process for the bank account.

Possible values:

* **valid**: the verification was successful.
* **pending**: the verification is in progress.
* **invalid**: the information provided is not complete.
* **rejected**:  there are reasons to refuse working with this entity.

## Enumeration

`VerificationStatus1Enum`

## Fields

| Name |
|  --- |
| `INVALID` |
| `PENDING` |
| `REJECTED` |
| `VALID` |

## Example

```php
use AdyenLib\Models\VerificationStatus1Enum;

$verificationStatus1 = VerificationStatus1Enum::INVALID;
```

