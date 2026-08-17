
# Route

## Structure

`Route`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `link` | `string` | Required | The redirection link. You can use this link to redirect the user to the open banking flow when the user selects it.<br><br>**Constraints**: *Minimum Length*: `1` | getLink(): string | setLink(string link): void |
| `provider` | [`Provider2`](../../doc/models/provider-2.md) | Required | Metadata about the selected provider, including the name and company logo. You can use this information to inform the user about the provider they will be redirected to when they select the link. | getProvider(): Provider2 | setProvider(Provider2 provider): void |

## Example

```php
use AdyenLib\Models\Builders\RouteBuilder;
use AdyenLib\Models\Builders\Provider2Builder;

$route = RouteBuilder::init(
    'link2',
    Provider2Builder::init(
        'logoURL6',
        'name8'
    )->build()
)->build();
```

