
# Givex Response Info 1

**givex** details

## Structure

`GivexResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currencyCode` | `?string` | Optional | The three-character ISO currency code | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |
| `password` | `?string` | Optional | The password provided by the acquirer. | getPassword(): ?string | setPassword(?string password): void |
| `paymentFlow` | `?string` | Optional | The sales channel used for the payment. | getPaymentFlow(): ?string | setPaymentFlow(?string paymentFlow): void |
| `username` | `?string` | Optional | The username provided by the acquirer. | getUsername(): ?string | setUsername(?string username): void |

## Example

```php
use AdyenLib\Models\Builders\GivexResponseInfo1Builder;

$givexResponseInfo1 = GivexResponseInfo1Builder::init()
    ->currencyCode('currencyCode6')
    ->password('password0')
    ->paymentFlow('paymentFlow4')
    ->username('username6')
    ->build();
```

