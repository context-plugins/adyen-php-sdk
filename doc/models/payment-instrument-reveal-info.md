
# Payment Instrument Reveal Info

## Structure

`PaymentInstrumentRevealInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cvc` | `string` | Required | The CVC2 value of the card. | getCvc(): string | setCvc(string cvc): void |
| `expiration` | [`Expiry2`](../../doc/models/expiry-2.md) | Required | The expiration date of the card. | getExpiration(): Expiry2 | setExpiration(Expiry2 expiration): void |
| `pan` | `string` | Required | The primary account number (PAN) of the card. | getPan(): string | setPan(string pan): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentRevealInfoBuilder;
use AdyenLib\Models\Builders\Expiry2Builder;

$paymentInstrumentRevealInfo = PaymentInstrumentRevealInfoBuilder::init(
    'cvc0',
    Expiry2Builder::init()
        ->month('month6')
        ->year('year8')
        ->build(),
    'pan2'
)->build();
```

