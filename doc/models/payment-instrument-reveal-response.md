
# Payment Instrument Reveal Response

## Structure

`PaymentInstrumentRevealResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `encryptedData` | `string` | Required | The data encrypted using the `encryptedKey`. | getEncryptedData(): string | setEncryptedData(string encryptedData): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentRevealResponseBuilder;

$paymentInstrumentRevealResponse = PaymentInstrumentRevealResponseBuilder::init(
    'encryptedData0'
)->build();
```

