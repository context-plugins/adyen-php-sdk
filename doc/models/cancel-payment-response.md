
# Cancel Payment Response

## Structure

`CancelPaymentResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`Links11`](../../doc/models/links-11.md) | Required | Contains redirection URLs to guide the user to the appropriate page, after a successful payment or a cancellation. | getLinks(): Links11 | setLinks(Links11 links): void |

## Example

```php
use AdyenLib\Models\Builders\CancelPaymentResponseBuilder;
use AdyenLib\Models\Builders\Links11Builder;
use AdyenLib\Models\Builders\Href6Builder;
use AdyenLib\Models\Builders\Href1Builder;

$cancelPaymentResponse = CancelPaymentResponseBuilder::init(
    Links11Builder::init()
        ->cancel(
            Href6Builder::init(
                'href4'
            )->build()
        )
        ->success(
            Href1Builder::init(
                'href2'
            )->build()
        )->build()
)->build();
```

