
# Terminal

## Structure

`Terminal`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `assignment` | [`?TerminalAssignment2`](../../doc/models/terminal-assignment-2.md) | Optional | Indicates the account level to which the terminal is assigned, the [assignment status](https://docs.adyen.com/point-of-sale/automating-terminal-management/assign-terminals-api), and where the terminals is in the process of being reassigned to. | getAssignment(): ?TerminalAssignment2 | setAssignment(?TerminalAssignment2 assignment): void |
| `cloudDeviceApiEndpoint` | `?string` | Optional | The [regional base URL](https://docs.adyen.com/api-explorer/terminal-api/1/overview#endpoints-for-cloud-communications) to use for sending Terminal API requests when using cloud communications. | getCloudDeviceApiEndpoint(): ?string | setCloudDeviceApiEndpoint(?string cloudDeviceApiEndpoint): void |
| `connectivity` | [`?TerminalConnectivity2`](../../doc/models/terminal-connectivity-2.md) | Optional | Information about bluetooth, cellular, ethernet and wifi connectivity for the terminal. | getConnectivity(): ?TerminalConnectivity2 | setConnectivity(?TerminalConnectivity2 connectivity): void |
| `countryCode` | `?string` | Optional | The country code of the country where the terminal is located. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `firmwareVersion` | `?string` | Optional | The software release currently in use on the terminal. | getFirmwareVersion(): ?string | setFirmwareVersion(?string firmwareVersion): void |
| `id` | `?string` | Optional | The unique identifier of the terminal. | getId(): ?string | setId(?string id): void |
| `installedAPKs` | [`?(InstalledAPKs[])`](../../doc/models/installed-ap-ks.md) | Optional | A list of Android apps installed on the terminal. | getInstalledAPKs(): ?array | setInstalledAPKs(?array installedAPKs): void |
| `lastActivityAt` | `?DateTime` | Optional | Date and time of the last activity on the terminal. Not included when the last activity was more than 14 days ago. | getLastActivityAt(): ?\DateTime | setLastActivityAt(?\DateTime lastActivityAt): void |
| `lastTransactionAt` | `?DateTime` | Optional | Date and time of the last transaction on the terminal. Not included when the last transaction was more than 14 days ago. | getLastTransactionAt(): ?\DateTime | setLastTransactionAt(?\DateTime lastTransactionAt): void |
| `model` | `?string` | Optional | The model name of the terminal. | getModel(): ?string | setModel(?string model): void |
| `restartLocalTime` | `?string` | Optional | The exact time of the terminal reboot, in the timezone of the terminal in **HH:mm** format. | getRestartLocalTime(): ?string | setRestartLocalTime(?string restartLocalTime): void |
| `serialNumber` | `?string` | Optional | The serial number of the terminal. | getSerialNumber(): ?string | setSerialNumber(?string serialNumber): void |

## Example

```php
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

$terminal = TerminalBuilder::init()
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
    ->cloudDeviceApiEndpoint('cloudDeviceApiEndpoint4')
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
    ->countryCode('countryCode2')
    ->firmwareVersion('firmwareVersion4')
    ->build();
```

