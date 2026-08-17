
# Checkout Three DS 2 Action

## Structure

`CheckoutThreeDS2Action`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorisationToken` | `?string` | Optional | A token needed to authorise a payment. | getAuthorisationToken(): ?string | setAuthorisationToken(?string authorisationToken): void |
| `paymentData` | `?string` | Optional | Encoded payment data. | getPaymentData(): ?string | setPaymentData(?string paymentData): void |
| `paymentMethodType` | `?string` | Optional | Specifies the payment method. | getPaymentMethodType(): ?string | setPaymentMethodType(?string paymentMethodType): void |
| `subtype` | `?string` | Optional | A subtype of the token. | getSubtype(): ?string | setSubtype(?string subtype): void |
| `token` | `?string` | Optional | A token to pass to the 3DS2 Component to get the fingerprint. | getToken(): ?string | setToken(?string token): void |
| `type` | `string` | Required, Constant | **threeDS2**<br><br>**Value**: `'threeDS2'` | getType(): string | setType(string type): void |
| `url` | `?string` | Optional | Specifies the URL to redirect to. | getUrl(): ?string | setUrl(?string url): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutThreeDS2ActionBuilder;

$checkoutThreeDS2Action = CheckoutThreeDS2ActionBuilder::init()
    ->authorisationToken('authorisationToken0')
    ->paymentData('paymentData8')
    ->paymentMethodType('paymentMethodType8')
    ->subtype('subtype8')
    ->token('token0')
    ->build();
```

