
# Checkout Forward Response from Url 2

The details of the response Adyen received from the third party.

## Structure

`CheckoutForwardResponseFromUrl2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `body` | `?string` | Optional | The body of the response Adyen received from the third party, in string format. | getBody(): ?string | setBody(?string body): void |
| `headers` | `?array<string,string>` | Optional | The HTTP headers of the response Adyen received from the third party. | getHeaders(): ?array | setHeaders(?array headers): void |
| `status` | `?int` | Optional | The HTTP status of the response Adyen received from the third party. | getStatus(): ?int | setStatus(?int status): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutForwardResponseFromUrl2Builder;

$checkoutForwardResponseFromUrl2 = CheckoutForwardResponseFromUrl2Builder::init()
    ->body('body4')
    ->headers(
        [
            'key0' => 'headers1'
        ]
    )
    ->status(122)
    ->build();
```

