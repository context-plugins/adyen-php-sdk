
# Identification Support Enum

Support of the loyalty account identification. Allows knowing where and how you have found the loyalty account identification.
Possible values:

* **NoCard**
* **LoyaltyCard**
* **HybridCard**
* **LinkedCard**

## Enumeration

`IdentificationSupportEnum`

## Fields

| Name |
|  --- |
| `NOCARD` |
| `LOYALTYCARD` |
| `HYBRIDCARD` |
| `LINKEDCARD` |

## Example

```php
use AdyenLib\Models\IdentificationSupportEnum;

$identificationSupport = IdentificationSupportEnum::NOCARD;
```

