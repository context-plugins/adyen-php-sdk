
# Stored Value Transaction Type 2 Enum

Identification of operation to proceed on the stored value account or the stored value card.
Copy.
Possible values:

* **Activate**
* **Duplicate**
* **Load**
* **Reserve**
* **Reverse**
* **Unload**

## Enumeration

`StoredValueTransactionType2Enum`

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
use AdyenLib\Models\StoredValueTransactionType2Enum;

$storedValueTransactionType2 = StoredValueTransactionType2Enum::LOAD;
```

