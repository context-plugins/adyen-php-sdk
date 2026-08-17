
# Check Tax Electronic Delivery Consent Response

## Structure

`CheckTaxElectronicDeliveryConsentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `uS1099k` | `?bool` | Optional | Consent to electronically deliver tax form US1099-K. | getUS1099k(): ?bool | setUS1099k(?bool uS1099k): void |

## Example

```php
use AdyenLib\Models\Builders\CheckTaxElectronicDeliveryConsentResponseBuilder;

$checkTaxElectronicDeliveryConsentResponse = CheckTaxElectronicDeliveryConsentResponseBuilder::init()
    ->uS1099k(false)
    ->build();
```

