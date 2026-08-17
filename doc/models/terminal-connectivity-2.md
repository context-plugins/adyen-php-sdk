
# Terminal Connectivity 2

Information about bluetooth, cellular, ethernet and wifi connectivity for the terminal.

## Structure

`TerminalConnectivity2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bluetooth` | [`?TerminalConnectivityBluetooth`](../../doc/models/terminal-connectivity-bluetooth.md) | Optional | - | getBluetooth(): ?TerminalConnectivityBluetooth | setBluetooth(?TerminalConnectivityBluetooth bluetooth): void |
| `cellular` | [`?TerminalConnectivityCellular`](../../doc/models/terminal-connectivity-cellular.md) | Optional | - | getCellular(): ?TerminalConnectivityCellular | setCellular(?TerminalConnectivityCellular cellular): void |
| `ethernet` | [`?TerminalConnectivityEthernet`](../../doc/models/terminal-connectivity-ethernet.md) | Optional | - | getEthernet(): ?TerminalConnectivityEthernet | setEthernet(?TerminalConnectivityEthernet ethernet): void |
| `wifi` | [`?TerminalConnectivityWifi`](../../doc/models/terminal-connectivity-wifi.md) | Optional | - | getWifi(): ?TerminalConnectivityWifi | setWifi(?TerminalConnectivityWifi wifi): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalConnectivity2Builder;
use AdyenLib\Models\Builders\TerminalConnectivityBluetoothBuilder;
use AdyenLib\Models\Builders\TerminalConnectivityCellularBuilder;
use AdyenLib\Models\Status31Enum;
use AdyenLib\Models\Builders\TerminalConnectivityEthernetBuilder;
use AdyenLib\Models\Builders\TerminalConnectivityWifiBuilder;

$terminalConnectivity2 = TerminalConnectivity2Builder::init()
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
    ->build();
```

