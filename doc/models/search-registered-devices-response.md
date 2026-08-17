
# Search Registered Devices Response

## Structure

`SearchRegisteredDevicesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(Device[])`](../../doc/models/device.md) | Optional | Contains a list of registered SCA devices and their corresponding details. | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `?int` | Optional | The total amount of registered SCA devices that match the query parameters. | getItemsTotal(): ?int | setItemsTotal(?int itemsTotal): void |
| `link` | [`?Link1`](../../doc/models/link-1.md) | Optional | Contains links to the list pages. | getLink(): ?Link1 | setLink(?Link1 link): void |
| `pagesTotal` | `?int` | Optional | The total amount of list pages. | getPagesTotal(): ?int | setPagesTotal(?int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\SearchRegisteredDevicesResponseBuilder;
use AdyenLib\Models\Builders\DeviceBuilder;
use AdyenLib\Models\Type101Enum;
use AdyenLib\Models\Builders\Link1Builder;
use AdyenLib\Models\Builders\LinksElementBuilder;

$searchRegisteredDevicesResponse = SearchRegisteredDevicesResponseBuilder::init()
    ->data(
        [
            DeviceBuilder::init()
                ->id('id0')
                ->name('name0')
                ->paymentInstrumentId('paymentInstrumentId2')
                ->type(Type101Enum::BROWSER)
                ->build(),
            DeviceBuilder::init()
                ->id('id0')
                ->name('name0')
                ->paymentInstrumentId('paymentInstrumentId2')
                ->type(Type101Enum::BROWSER)
                ->build()
        ]
    )
    ->itemsTotal(202)
    ->link(
        Link1Builder::init()
            ->first(
                LinksElementBuilder::init()
                    ->href('href2')
                    ->build()
            )
            ->last(
                LinksElementBuilder::init()
                    ->href('href2')
                    ->build()
            )
            ->next(
                LinksElementBuilder::init()
                    ->href('href4')
                    ->build()
            )
            ->previous(
                LinksElementBuilder::init()
                    ->href('href0')
                    ->build()
            )
            ->self(
                LinksElementBuilder::init()
                    ->href('href0')
                    ->build()
            )
            ->build()
    )
    ->pagesTotal(92)
    ->build();
```

