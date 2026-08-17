
# Payment Details Request 1

## Structure

`PaymentDetailsRequest1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | `?string` | Optional | - | getMethod(): ?string | setMethod(?string method): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentDetailsRequest1Builder;

$paymentDetailsRequest1 = PaymentDetailsRequest1Builder::init()
    ->method('PaymentDetailsRequest')
    ->build();
```

