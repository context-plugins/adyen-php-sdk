
# Payment Instrument 2

## Structure

`PaymentInstrument2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | The description of the resource. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the resource. | getId(): ?string | setId(?string id): void |
| `reference` | `?string` | Optional | The reference for the resource. | getReference(): ?string | setReference(?string reference): void |
| `tokenType` | `?string` | Optional | The type of wallet that the network token is associated with. | getTokenType(): ?string | setTokenType(?string tokenType): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrument2Builder;

$paymentInstrument2 = PaymentInstrument2Builder::init()
    ->description('description0')
    ->id('id0')
    ->reference('reference4')
    ->tokenType('tokenType4')
    ->build();
```

