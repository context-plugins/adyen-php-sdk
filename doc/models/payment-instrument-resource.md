
# Payment Instrument Resource

## Structure

`PaymentInstrumentResource`

## Inherits From

[`Resource2`](../../doc/models/resource-2.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Required | **Constraints**: *Minimum Length*: `1` | getPaymentInstrumentId(): string | setPaymentInstrumentId(string paymentInstrumentId): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentResourceBuilder;

$paymentInstrumentResource = PaymentInstrumentResourceBuilder::init(
    'paymentInstrumentId4'
)
    ->type('paymentInstrument')
    ->build();
```

