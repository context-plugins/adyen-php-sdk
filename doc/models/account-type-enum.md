
# Account Type Enum

Indicates the type of account. For example, for a multi-account card product.
Allowed values:

* notApplicable
* credit
* debit

## Enumeration

`AccountTypeEnum`

## Fields

| Name |
|  --- |
| `NOTAPPLICABLE` |
| `CREDIT` |
| `DEBIT` |

## Example

```php
use AdyenLib\Models\AccountTypeEnum;

$accountType = AccountTypeEnum::DEBIT;
```

