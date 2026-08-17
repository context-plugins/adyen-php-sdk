
# Payment Response 3

Only returned for `resultCode`: **Authorised**.
Details about the payment method used in the transaction.

## Structure

`PaymentResponse3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `brand` | `?string` | Optional | The card brand that the shopper used to pay. Only returned if `paymentMethod.type` is **scheme**. | getBrand(): ?string | setBrand(?string brand): void |
| `type` | `?string` | Optional | The `paymentMethod.type` value used in the request. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentResponse3Builder;

$paymentResponse3 = PaymentResponse3Builder::init()
    ->brand('brand6')
    ->type('type2')
    ->build();
```

