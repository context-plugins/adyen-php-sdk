
# Paypal Update Order Response

## Structure

`PaypalUpdateOrderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentData` | `string` | Required | The updated paymentData. | getPaymentData(): string | setPaymentData(string paymentData): void |
| `status` | [`string(Status4Enum)`](../../doc/models/status-4-enum.md) | Required | The status of the request. This indicates whether the order was successfully updated with PayPal. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\PaypalUpdateOrderResponseBuilder;
use AdyenLib\Models\Status4Enum;

$paypalUpdateOrderResponse = PaypalUpdateOrderResponseBuilder::init(
    'paymentData0',
    Status4Enum::ERROR
)->build();
```

