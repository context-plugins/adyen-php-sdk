
# Filter Merchant Account Type 1 Enum

Shows how merchant accounts are included in company-level webhooks. Possible values:

* **includeAccounts**
* **excludeAccounts**
* **allAccounts**: Includes all merchant accounts, and does not require specifying `filterMerchantAccounts`.

## Enumeration

`FilterMerchantAccountType1Enum`

## Fields

| Name |
|  --- |
| `ALLACCOUNTS` |
| `EXCLUDEACCOUNTS` |
| `INCLUDEACCOUNTS` |

## Example

```php
use AdyenLib\Models\FilterMerchantAccountType1Enum;

$filterMerchantAccountType1 = FilterMerchantAccountType1Enum::EXCLUDEACCOUNTS;
```

