
# Agency

## Structure

`Agency`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `invoiceNumber` | `?string` | Optional | The reference number for the invoice, issued by the agency.<br><br>* Encoding: ASCII<br>* minLength: 1 character<br>* maxLength: 6 characters<br>* **additionalData key:** `airline.agency_invoice_number` | getInvoiceNumber(): ?string | setInvoiceNumber(?string invoiceNumber): void |
| `planName` | `?string` | Optional | The two-letter agency plan identifier.<br><br>* Encoding: ASCII<br>* minLength: 2 characters<br>* maxLength: 2 characters<br>* **additionalData key:** `airline.agency_plan_name` | getPlanName(): ?string | setPlanName(?string planName): void |

## Example

```php
use AdyenLib\Models\Builders\AgencyBuilder;

$agency = AgencyBuilder::init()
    ->invoiceNumber('invoiceNumber6')
    ->planName('planName6')
    ->build();
```

