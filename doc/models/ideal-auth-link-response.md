
# Ideal Auth Link Response

## Structure

`IdealAuthLinkResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `redirectUrl` | [`?Href3`](../../doc/models/href-3.md) | Optional | A short-lived URL that redirects the user to the iDEAL profile management page. | getRedirectUrl(): ?Href3 | setRedirectUrl(?Href3 redirectUrl): void |

## Example

```php
use AdyenLib\Models\Builders\IdealAuthLinkResponseBuilder;
use AdyenLib\Models\Builders\Href3Builder;

$idealAuthLinkResponse = IdealAuthLinkResponseBuilder::init()
    ->redirectUrl(
        Href3Builder::init(
            'href8'
        )->build()
    )->build();
```

