
# Identification Support 1 Enum

Support of the loyalty account identification. Allows knowing where and how you have found the loyalty account identification.
Possible values:

* **HybridCard**
* **LinkedCard**
* **LoyaltyCard**
* **NoCard**

## Enumeration

`IdentificationSupport1Enum`

## Fields

| Name |
|  --- |
| `NOCARD` |
| `LOYALTYCARD` |
| `HYBRIDCARD` |
| `LINKEDCARD` |

## Example

```php
use AdyenLib\Models\IdentificationSupport1Enum;

$identificationSupport1 = IdentificationSupport1Enum::NOCARD;
```

