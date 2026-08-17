
# Terminal Connectivity Bluetooth

## Structure

`TerminalConnectivityBluetooth`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ipAddress` | `?string` | Optional | The terminal's Bluetooth IP address. | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |
| `macAddress` | `?string` | Optional | The terminal's Bluetooth MAC address. | getMacAddress(): ?string | setMacAddress(?string macAddress): void |

## Example

```php
use AdyenLib\Models\Builders\TerminalConnectivityBluetoothBuilder;

$terminalConnectivityBluetooth = TerminalConnectivityBluetoothBuilder::init()
    ->ipAddress('ipAddress6')
    ->macAddress('macAddress8')
    ->build();
```

