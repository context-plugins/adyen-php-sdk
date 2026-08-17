
# Merchant Refund Reason Enum

The reason for the refund request.

Possible values:

* **FRAUD**

* **CUSTOMER REQUEST**

* **RETURN**

* **DUPLICATE**

* **OTHER**

## Enumeration

`MerchantRefundReasonEnum`

## Fields

| Name |
|  --- |
| `FRAUD` |
| `ENUM_CUSTOMER_REQUEST` |
| `RETURN_` |
| `DUPLICATE` |
| `OTHER` |

## Example

```php
use AdyenLib\Models\MerchantRefundReasonEnum;

$merchantRefundReason = MerchantRefundReasonEnum::FRAUD;
```

