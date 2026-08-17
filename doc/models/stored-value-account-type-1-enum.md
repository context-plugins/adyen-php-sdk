
# Stored Value Account Type 1 Enum

Type of stored value account. Allows the distinction of the stored value instrument to access the stored value account.
Possible values:

* **GiftCard**
* **Other**
* **PhoneCard**

## Enumeration

`StoredValueAccountType1Enum`

## Fields

| Name |
|  --- |
| `GIFTCARD` |
| `PHONECARD` |
| `OTHER` |

## Example

```php
use AdyenLib\Models\StoredValueAccountType1Enum;

$storedValueAccountType1 = StoredValueAccountType1Enum::OTHER;
```

