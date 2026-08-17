
# Stored Value Transaction Type 1 Enum

Identification of operation to proceed on the stored value account or the stored value card.
Possible values:

* **Activate**
* **Duplicate**
* **Load**
* **Reserve**
* **Reverse**
* **Unload**

## Enumeration

`StoredValueTransactionType1Enum`

## Fields

| Name |
|  --- |
| `RESERVE` |
| `ACTIVATE` |
| `LOAD` |
| `UNLOAD` |
| `REVERSE` |
| `DUPLICATE` |

## Example

```php
use AdyenLib\Models\StoredValueTransactionType1Enum;

$storedValueTransactionType1 = StoredValueTransactionType1Enum::LOAD;
```

