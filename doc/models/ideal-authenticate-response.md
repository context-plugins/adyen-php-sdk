
# Ideal Authenticate Response

## Structure

`IdealAuthenticateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `redirectUrl` | [`?Href4`](../../doc/models/href-4.md) | Optional | A short-lived URL that redirects the user to the iDEAL page that is required for authentication. | getRedirectUrl(): ?Href4 | setRedirectUrl(?Href4 redirectUrl): void |

## Example

```php
use AdyenLib\Models\Builders\IdealAuthenticateResponseBuilder;
use AdyenLib\Models\Builders\Href4Builder;

$idealAuthenticateResponse = IdealAuthenticateResponseBuilder::init()
    ->redirectUrl(
        Href4Builder::init(
            'href8'
        )->build()
    )->build();
```

