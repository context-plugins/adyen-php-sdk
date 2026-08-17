
# List Terminals Response

## Structure

`ListTerminalsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `data` | [`?(Terminal[])`](../../doc/models/terminal.md) | Optional | The list of terminals and their details. | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |

## Example

```php
use AdyenLib\Models\Builders\ListTerminalsResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\TerminalBuilder;
use AdyenLib\Models\Builders\TerminalAssignment2Builder;
use AdyenLib\Models\Status21Enum;
use AdyenLib\Models\Builders\TerminalReassignmentTarget2Builder;
use AdyenLib\Models\Builders\TerminalConnectivity2Builder;
use AdyenLib\Models\Builders\TerminalConnectivityBluetoothBuilder;
use AdyenLib\Models\Builders\TerminalConnectivityCellularBuilder;
use AdyenLib\Models\Status31Enum;
use AdyenLib\Models\Builders\TerminalConnectivityEthernetBuilder;
use AdyenLib\Models\Builders\TerminalConnectivityWifiBuilder;

$listTerminalsResponse = ListTerminalsResponseBuilder::init(
    226,
    68
)
    ->links(
        PaginationLinks1Builder::init(
            LinksElement9Builder::init()
                ->href('href2')
                ->build(),
            LinksElement10Builder::init()
                ->href('href2')
                ->build(),
            LinksElement13Builder::init()
                ->href('href0')
                ->build()
        )
            ->next(
                LinksElement11Builder::init()
                    ->href('href4')
                    ->build()
            )
            ->prev(
                LinksElement12Builder::init()
                    ->href('href8')
                    ->build()
            )
            ->build()
    )
    ->data(
        [
            TerminalBuilder::init()
                ->assignment(
                    TerminalAssignment2Builder::init(
                        'companyId6',
                        Status21Enum::INVENTORY
                    )
                        ->merchantId('merchantId2')
                        ->reassignmentTarget(
                            TerminalReassignmentTarget2Builder::init(
                                false
                            )
                                ->companyId('companyId4')
                                ->merchantId('merchantId0')
                                ->storeId('storeId8')
                                ->build()
                        )
                        ->storeId('storeId0')
                        ->build()
                )
                ->cloudDeviceApiEndpoint('cloudDeviceApiEndpoint2')
                ->connectivity(
                    TerminalConnectivity2Builder::init()
                        ->bluetooth(
                            TerminalConnectivityBluetoothBuilder::init()
                                ->ipAddress('ipAddress2')
                                ->macAddress('macAddress2')
                                ->build()
                        )
                        ->cellular(
                            TerminalConnectivityCellularBuilder::init()
                                ->iccid('iccid6')
                                ->iccid2('iccid24')
                                ->status(Status31Enum::DEPRECATED)
                                ->build()
                        )
                        ->ethernet(
                            TerminalConnectivityEthernetBuilder::init()
                                ->ipAddress('ipAddress2')
                                ->linkNegotiation('linkNegotiation6')
                                ->macAddress('macAddress2')
                                ->build()
                        )
                        ->wifi(
                            TerminalConnectivityWifiBuilder::init()
                                ->ipAddress('ipAddress8')
                                ->macAddress('macAddress6')
                                ->ssid('ssid4')
                                ->build()
                        )
                        ->build()
                )
                ->countryCode('countryCode6')
                ->firmwareVersion('firmwareVersion2')
                ->build(),
            TerminalBuilder::init()
                ->assignment(
                    TerminalAssignment2Builder::init(
                        'companyId6',
                        Status21Enum::INVENTORY
                    )
                        ->merchantId('merchantId2')
                        ->reassignmentTarget(
                            TerminalReassignmentTarget2Builder::init(
                                false
                            )
                                ->companyId('companyId4')
                                ->merchantId('merchantId0')
                                ->storeId('storeId8')
                                ->build()
                        )
                        ->storeId('storeId0')
                        ->build()
                )
                ->cloudDeviceApiEndpoint('cloudDeviceApiEndpoint2')
                ->connectivity(
                    TerminalConnectivity2Builder::init()
                        ->bluetooth(
                            TerminalConnectivityBluetoothBuilder::init()
                                ->ipAddress('ipAddress2')
                                ->macAddress('macAddress2')
                                ->build()
                        )
                        ->cellular(
                            TerminalConnectivityCellularBuilder::init()
                                ->iccid('iccid6')
                                ->iccid2('iccid24')
                                ->status(Status31Enum::DEPRECATED)
                                ->build()
                        )
                        ->ethernet(
                            TerminalConnectivityEthernetBuilder::init()
                                ->ipAddress('ipAddress2')
                                ->linkNegotiation('linkNegotiation6')
                                ->macAddress('macAddress2')
                                ->build()
                        )
                        ->wifi(
                            TerminalConnectivityWifiBuilder::init()
                                ->ipAddress('ipAddress8')
                                ->macAddress('macAddress6')
                                ->ssid('ssid4')
                                ->build()
                        )
                        ->build()
                )
                ->countryCode('countryCode6')
                ->firmwareVersion('firmwareVersion2')
                ->build()
        ]
    )
    ->build();
```

