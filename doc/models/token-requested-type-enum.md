
# Token Requested Type Enum

Type of token replacing the PAN of a payment card to identify the payment mean of the customer. It allows, for a merchant, to use a token for a transaction only or for a longer period.
Possible values:

* **Transaction**
* **Customer**

## Enumeration

`TokenRequestedTypeEnum`

## Fields

| Name |
|  --- |
| `TRANSACTION` |
| `CUSTOMER` |

## Example

```php
use AdyenLib\Models\TokenRequestedTypeEnum;

$tokenRequestedType = TokenRequestedTypeEnum::TRANSACTION;
```

