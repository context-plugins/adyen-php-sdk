
# Contract Type Enum

The contract type of the grant offer. Possible value: **cashAdvance**, **loan**., The contract type of the offer.

Possible values:

* **loan**
* **cashAdvance**

## Enumeration

`ContractTypeEnum`

## Fields

| Name |
|  --- |
| `CASHADVANCE` |
| `LOAN` |

## Example

```php
use AdyenLib\Models\ContractTypeEnum;

$contractType = ContractTypeEnum::CASHADVANCE;
```

