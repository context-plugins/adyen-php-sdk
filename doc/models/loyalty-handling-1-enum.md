
# Loyalty Handling 1 Enum

Type of Loyalty processing requested by the Sale System.
Possible values:

* **Allowed**
* **Forbidden**
* **Processed**
* **Proposed**
* **Required**

## Enumeration

`LoyaltyHandling1Enum`

## Fields

| Name |
|  --- |
| `FORBIDDEN` |
| `PROCESSED` |
| `ALLOWED` |
| `PROPOSED` |
| `REQUIRED` |

## Example

```php
use AdyenLib\Models\LoyaltyHandling1Enum;

$loyaltyHandling1 = LoyaltyHandling1Enum::FORBIDDEN;
```

