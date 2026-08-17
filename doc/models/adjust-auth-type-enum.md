
# Adjust Auth Type Enum

The type of adjustment. Possible values:

* **cardholderInitiatedTransaction**

* **merchantInitiatedTransaction**

## Enumeration

`AdjustAuthTypeEnum`

## Fields

| Name |
|  --- |
| `CARDHOLDERINITIATEDTRANSACTION` |
| `MERCHANTINITIATEDTRANSACTION` |

## Example

```php
use AdyenLib\Models\AdjustAuthTypeEnum;

$adjustAuthType = AdjustAuthTypeEnum::CARDHOLDERINITIATEDTRANSACTION;
```

