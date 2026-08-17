
# Loyalty Handling 2 Enum

Type of Loyalty processing requested by the Sale System. An way to specify what the POI has to handle concerning the loyalty.
Possible values:

* **Allowed**
* **Forbidden**
* **Processed**
* **Proposed**
* **Required**

## Enumeration

`LoyaltyHandling2Enum`

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
use AdyenLib\Models\LoyaltyHandling2Enum;

$loyaltyHandling2 = LoyaltyHandling2Enum::PROCESSED;
```

