
# Givex Info

## Structure

`GivexInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currencyCode` | `string` | Required | The three-character ISO currency code, such as **EUR**. | getCurrencyCode(): string | setCurrencyCode(string currencyCode): void |
| `password` | `string` | Required | The password provided by the acquirer. | getPassword(): string | setPassword(string password): void |
| `paymentFlow` | [`string(PaymentFlowEnum)`](../../doc/models/payment-flow-enum.md) | Required | The sales channel used for the payment. | getPaymentFlow(): string | setPaymentFlow(string paymentFlow): void |
| `username` | `string` | Required | The username provided by the acquirer. | getUsername(): string | setUsername(string username): void |

## Example

```php
use AdyenLib\Models\Builders\GivexInfoBuilder;
use AdyenLib\Models\PaymentFlowEnum;

$givexInfo = GivexInfoBuilder::init(
    'currencyCode6',
    'password0',
    PaymentFlowEnum::ECOMMERCE,
    'username6'
)->build();
```

