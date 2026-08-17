
# Payment Instrument 21

Contains information about the payment instrument that was used for the transaction.

## Structure

`PaymentInstrument21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The description of the resource. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the resource. | getId(): ?string | setId(?string id): void |
| `reference` | `?string` | Optional | The reference for the resource. | getReference(): ?string | setReference(?string reference): void |
| `tokenType` | `?string` | Optional | The type of wallet that the network token is associated with. | getTokenType(): ?string | setTokenType(?string tokenType): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrument21Builder;

$paymentInstrument21 = PaymentInstrument21Builder::init()
    ->description('description2')
    ->id('id8')
    ->reference('reference6')
    ->tokenType('tokenType6')
    ->build();
```

