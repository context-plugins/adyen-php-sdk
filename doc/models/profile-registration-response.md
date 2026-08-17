
# Profile Registration Response

## Structure

`ProfileRegistrationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `redirectUrl` | [`?Href5`](../../doc/models/href-5.md) | Optional | A short-lived URL that redirects the user to the iDEAL profile registration page. | getRedirectUrl(): ?Href5 | setRedirectUrl(?Href5 redirectUrl): void |

## Example

```php
use AdyenLib\Models\Builders\ProfileRegistrationResponseBuilder;
use AdyenLib\Models\Builders\Href5Builder;

$profileRegistrationResponse = ProfileRegistrationResponseBuilder::init()
    ->redirectUrl(
        Href5Builder::init(
            'href8'
        )->build()
    )->build();
```

