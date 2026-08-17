
# Company Links 2

References to resources connected with this company.

## Structure

`CompanyLinks2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `apiCredentials` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | - | getApiCredentials(): ?LinksElement | setApiCredentials(?LinksElement apiCredentials): void |
| `self` | [`LinksElement6`](../../doc/models/links-element-6.md) | Required | Link to the resource itself. | getSelf(): LinksElement6 | setSelf(LinksElement6 self): void |
| `users` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | - | getUsers(): ?LinksElement | setUsers(?LinksElement users): void |
| `webhooks` | [`?LinksElement`](../../doc/models/links-element.md) | Optional | - | getWebhooks(): ?LinksElement | setWebhooks(?LinksElement webhooks): void |

## Example

```php
use AdyenLib\Models\Builders\CompanyLinks2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;

$companyLinks2 = CompanyLinks2Builder::init(
    LinksElement6Builder::init()
        ->href('href0')
        ->build()
)
    ->apiCredentials(
        LinksElementBuilder::init()
            ->href('href8')
            ->build()
    )
    ->users(
        LinksElementBuilder::init()
            ->href('href8')
            ->build()
    )
    ->webhooks(
        LinksElementBuilder::init()
            ->href('href8')
            ->build()
    )
    ->build();
```

