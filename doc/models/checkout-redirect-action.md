
# Checkout Redirect Action

## Structure

`CheckoutRedirectAction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | `?array<string,string>` | Optional | When the redirect URL must be accessed via POST, use this data to post to the redirect URL. | getData(): ?array | setData(?array data): void |
| `method` | `?string` | Optional | Specifies the HTTP method, for example GET or POST. | getMethod(): ?string | setMethod(?string method): void |
| `paymentMethodType` | `?string` | Optional | Specifies the payment method. | getPaymentMethodType(): ?string | setPaymentMethodType(?string paymentMethodType): void |
| `type` | `string` | Required, Constant | **redirect**<br><br>**Value**: `'redirect'` | getType(): string | setType(string type): void |
| `url` | `?string` | Optional | Specifies the URL to redirect to. | getUrl(): ?string | setUrl(?string url): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutRedirectActionBuilder;

$checkoutRedirectAction = CheckoutRedirectActionBuilder::init()
    ->data(
        [
            'key0' => 'data3',
            'key1' => 'data4'
        ]
    )
    ->method('method2')
    ->paymentMethodType('paymentMethodType0')
    ->url('url2')
    ->build();
```

