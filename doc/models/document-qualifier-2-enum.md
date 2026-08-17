
# Document Qualifier 2 Enum

Qualification of the document to print to the Cashier or the Customer. Allows the manager of the printer, Sale or POI Terminal, to send information to a physical printer or to use the paper type accordingly.
Possible values:

* **CashierReceipt**
* **CustomerReceipt**
* **Document**
* **Journal**
* **SaleReceipt**
* **Voucher**

## Enumeration

`DocumentQualifier2Enum`

## Fields

| Name |
|  --- |
| `SALERECEIPT` |
| `CASHIERRECEIPT` |
| `CUSTOMERRECEIPT` |
| `DOCUMENT` |
| `VOUCHER` |
| `JOURNAL` |

## Example

```php
use AdyenLib\Models\DocumentQualifier2Enum;

$documentQualifier2 = DocumentQualifier2Enum::SALERECEIPT;
```

