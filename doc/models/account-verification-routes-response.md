
# Account Verification Routes Response

## Structure

`AccountVerificationRoutesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `routes` | [`Route[]`](../../doc/models/route.md) | Required | This array lists available open banking redirection links, each with its associated provider metadata. | getRoutes(): array | setRoutes(array routes): void |

## Example

```php
use AdyenLib\Models\Builders\AccountVerificationRoutesResponseBuilder;
use AdyenLib\Models\Builders\RouteBuilder;
use AdyenLib\Models\Builders\Provider2Builder;

$accountVerificationRoutesResponse = AccountVerificationRoutesResponseBuilder::init(
    [
        RouteBuilder::init(
            'link6',
            Provider2Builder::init(
                'logoURL6',
                'name8'
            )->build()
        )->build()
    ]
)->build();
```

