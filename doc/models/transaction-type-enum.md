
# Transaction Type Enum

Identify the type of the transaction being authenticated.

## Enumeration

`TransactionTypeEnum`

## Fields

| Name |
|  --- |
| `GOODSORSERVICEPURCHASE` |
| `CHECKACCEPTANCE` |
| `ACCOUNTFUNDING` |
| `QUASICASHTRANSACTION` |
| `PREPAIDACTIVATIONANDLOAD` |

## Example

```php
use AdyenLib\Models\TransactionTypeEnum;

$transactionType = TransactionTypeEnum::PREPAIDACTIVATIONANDLOAD;
```

