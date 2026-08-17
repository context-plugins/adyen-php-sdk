
# Givex Response Info

## Structure

`GivexResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currencyCode` | `?string` | Optional | The three-character ISO currency code | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |
| `password` | `?string` | Optional | The password provided by the acquirer. | getPassword(): ?string | setPassword(?string password): void |
| `paymentFlow` | `?string` | Optional | The sales channel used for the payment. | getPaymentFlow(): ?string | setPaymentFlow(?string paymentFlow): void |
| `username` | `?string` | Optional | The username provided by the acquirer. | getUsername(): ?string | setUsername(?string username): void |

## Example

```php
use AdyenLib\Models\Builders\GivexResponseInfoBuilder;

$givexResponseInfo = GivexResponseInfoBuilder::init()
    ->currencyCode('currencyCode2')
    ->password('password6')
    ->paymentFlow('paymentFlow0')
    ->username('username8')
    ->build();
```

