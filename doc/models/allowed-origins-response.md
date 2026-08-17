
# Allowed Origins Response

## Structure

`AllowedOriginsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(AllowedOrigin[])`](../../doc/models/allowed-origin.md) | Optional | List of allowed origins. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\AllowedOriginsResponseBuilder;
use AdyenLib\Models\Builders\AllowedOriginBuilder;
use AdyenLib\Models\Builders\Links2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;

$allowedOriginsResponse = AllowedOriginsResponseBuilder::init()
    ->data(
        [
            AllowedOriginBuilder::init(
                'domain6'
            )
                ->links(
                    Links2Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )->build()
                )
                ->id('id0')
                ->build()
        ]
    )
    ->build();
```

