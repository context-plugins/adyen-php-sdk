
# Payment Instrument 3

Contains information about the payment instrument used in the transfer.

## Structure

`PaymentInstrument3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The description of the resource. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the resource. | getId(): ?string | setId(?string id): void |
| `reference` | `?string` | Optional | The reference for the resource. | getReference(): ?string | setReference(?string reference): void |
| `tokenType` | `?string` | Optional | The type of wallet that the network token is associated with. | getTokenType(): ?string | setTokenType(?string tokenType): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrument3Builder;

$paymentInstrument3 = PaymentInstrument3Builder::init()
    ->description('description6')
    ->id('id6')
    ->reference('reference2')
    ->tokenType('tokenType2')
    ->build();
```

