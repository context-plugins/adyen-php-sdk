
# Mandate Update

## Structure

`MandateUpdate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentInstrumentId` | `?string` | Optional | The unique identifier of the payment instrument linked to the mandate. | getPaymentInstrumentId(): ?string | setPaymentInstrumentId(?string paymentInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\MandateUpdateBuilder;

$mandateUpdate = MandateUpdateBuilder::init()
    ->paymentInstrumentId('paymentInstrumentId4')
    ->build();
```

