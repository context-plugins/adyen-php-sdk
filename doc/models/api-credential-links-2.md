
# Api Credential Links 2

References to resources linked to the API credential.

## Structure

`ApiCredentialLinks2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowedOrigins` | [`?LinksElement1`](../../doc/models/links-element-1.md) | Optional | List of allowed origins. | getAllowedOrigins(): ?LinksElement1 | setAllowedOrigins(?LinksElement1 allowedOrigins): void |
| `company` | [`?LinksElement2`](../../doc/models/links-element-2.md) | Optional | Company account that the API credential is linked to. Only present for company-level webhooks. | getCompany(): ?LinksElement2 | setCompany(?LinksElement2 company): void |
| `generateApiKey` | [`?LinksElement3`](../../doc/models/links-element-3.md) | Optional | Generates a new API key. When you generate a new one, the existing key remains valid for 24 hours. | getGenerateApiKey(): ?LinksElement3 | setGenerateApiKey(?LinksElement3 generateApiKey): void |
| `generateClientKey` | [`?LinksElement4`](../../doc/models/links-element-4.md) | Optional | Generates a new client key, used to authenticate client-side requests. When you generate a new one, the existing key remains valid for 24 hours. | getGenerateClientKey(): ?LinksElement4 | setGenerateClientKey(?LinksElement4 generateClientKey): void |
| `merchant` | [`?LinksElement5`](../../doc/models/links-element-5.md) | Optional | The merchant account that the API credential is linked to. Only present for merchant-level API credentials. | getMerchant(): ?LinksElement5 | setMerchant(?LinksElement5 merchant): void |
| `self` | [`LinksElement6`](../../doc/models/links-element-6.md) | Required | Link to the resource itself. | getSelf(): LinksElement6 | setSelf(LinksElement6 self): void |

## Example

```php
use AdyenLib\Models\Builders\ApiCredentialLinks2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\LinksElement1Builder;
use AdyenLib\Models\Builders\LinksElement2Builder;
use AdyenLib\Models\Builders\LinksElement3Builder;
use AdyenLib\Models\Builders\LinksElement4Builder;
use AdyenLib\Models\Builders\LinksElement5Builder;

$apiCredentialLinks2 = ApiCredentialLinks2Builder::init(
    LinksElement6Builder::init()
        ->href('href0')
        ->build()
)
    ->allowedOrigins(
        LinksElement1Builder::init()
            ->href('href6')
            ->build()
    )
    ->company(
        LinksElement2Builder::init()
            ->href('href2')
            ->build()
    )
    ->generateApiKey(
        LinksElement3Builder::init()
            ->href('href6')
            ->build()
    )
    ->generateClientKey(
        LinksElement4Builder::init()
            ->href('href4')
            ->build()
    )
    ->merchant(
        LinksElement5Builder::init()
            ->href('href6')
            ->build()
    )
    ->build();
```

