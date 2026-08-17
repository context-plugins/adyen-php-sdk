
# Links 11

Contains redirection URLs to guide the user to the appropriate page, after a successful payment or a cancellation.

## Structure

`Links11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cancel` | [`?Href6`](../../doc/models/href-6.md) | Optional | The URL to where the user must be redirected after a payment has been canceled. | getCancel(): ?Href6 | setCancel(?Href6 cancel): void |
| `success` | [`?Href1`](../../doc/models/href-1.md) | Optional | The URL to where the user must be redirected after a successful payment. | getSuccess(): ?Href1 | setSuccess(?Href1 success): void |

## Example

```php
use AdyenLib\Models\Builders\Links11Builder;
use AdyenLib\Models\Builders\Href6Builder;
use AdyenLib\Models\Builders\Href1Builder;

$links11 = Links11Builder::init()
    ->cancel(
        Href6Builder::init(
            'href4'
        )->build()
    )
    ->success(
        Href1Builder::init(
            'href2'
        )->build()
    )->build();
```

