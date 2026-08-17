
# Get Terminal Details Response

## Structure

`GetTerminalDetailsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bluetoothIp` | `?string` | Optional | The Bluetooth IP address of the terminal. | getBluetoothIp(): ?string | setBluetoothIp(?string bluetoothIp): void |
| `bluetoothMac` | `?string` | Optional | The Bluetooth MAC address of the terminal. | getBluetoothMac(): ?string | setBluetoothMac(?string bluetoothMac): void |
| `companyAccount` | `string` | Required | The company account that the terminal is associated with. If this is the only account level shown in the response, the terminal is assigned to the inventory of the company account. | getCompanyAccount(): string | setCompanyAccount(string companyAccount): void |
| `country` | `?string` | Optional | The country where the terminal is used. | getCountry(): ?string | setCountry(?string country): void |
| `deviceModel` | `?string` | Optional | The model name of the terminal. | getDeviceModel(): ?string | setDeviceModel(?string deviceModel): void |
| `dhcpEnabled` | `?bool` | Optional | Indicates whether assigning IP addresses through a DHCP server is enabled on the terminal. | getDhcpEnabled(): ?bool | setDhcpEnabled(?bool dhcpEnabled): void |
| `displayLabel` | `?string` | Optional | The label shown on the status bar of the display. This label (if any) is specified in your Customer Area. | getDisplayLabel(): ?string | setDisplayLabel(?string displayLabel): void |
| `ethernetIp` | `?string` | Optional | The terminal's IP address in your Ethernet network. | getEthernetIp(): ?string | setEthernetIp(?string ethernetIp): void |
| `ethernetMac` | `?string` | Optional | The terminal's MAC address in your Ethernet network. | getEthernetMac(): ?string | setEthernetMac(?string ethernetMac): void |
| `firmwareVersion` | `?string` | Optional | The software release currently in use on the terminal. | getFirmwareVersion(): ?string | setFirmwareVersion(?string firmwareVersion): void |
| `iccid` | `?string` | Optional | The integrated circuit card identifier (ICCID) of the SIM card in the terminal. | getIccid(): ?string | setIccid(?string iccid): void |
| `lastActivityDateTime` | `?DateTime` | Optional | Date and time of the last activity on the terminal. Not included when the last activity was more than 14 days ago. | getLastActivityDateTime(): ?\DateTime | setLastActivityDateTime(?\DateTime lastActivityDateTime): void |
| `lastTransactionDateTime` | `?DateTime` | Optional | Date and time of the last transaction on the terminal. Not included when the last transaction was more than 14 days ago. | getLastTransactionDateTime(): ?\DateTime | setLastTransactionDateTime(?\DateTime lastTransactionDateTime): void |
| `linkNegotiation` | `?string` | Optional | The Ethernet link negotiation that the terminal uses:<br><br>- `auto`: Auto-negotiation<br><br>- `100full`: 100 Mbps full duplex | getLinkNegotiation(): ?string | setLinkNegotiation(?string linkNegotiation): void |
| `merchantAccount` | `?string` | Optional | The merchant account that the terminal is associated with. If the response doesn't contain a `store` the terminal is assigned to this merchant account. | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |
| `merchantInventory` | `?bool` | Optional | Boolean that indicates if the terminal is assigned to the merchant inventory. This is returned when the terminal is assigned to a merchant account.<br><br>- If **true**, this indicates that the terminal is in the merchant inventory. This also means that the terminal cannot be boarded.<br><br>- If **false**, this indicates that the terminal is assigned to the merchant account as an in-store terminal. This means that the terminal is ready to be boarded, or is already boarded. | getMerchantInventory(): ?bool | setMerchantInventory(?bool merchantInventory): void |
| `permanentTerminalId` | `?string` | Optional | The permanent terminal ID. | getPermanentTerminalId(): ?string | setPermanentTerminalId(?string permanentTerminalId): void |
| `serialNumber` | `?string` | Optional | The serial number of the terminal. | getSerialNumber(): ?string | setSerialNumber(?string serialNumber): void |
| `simStatus` | `?string` | Optional | On a terminal that supports 3G or 4G connectivity, indicates the status of the SIM card in the terminal: ACTIVE or INVENTORY. | getSimStatus(): ?string | setSimStatus(?string simStatus): void |
| `store` | `?string` | Optional | The store code of the store that the terminal is assigned to. | getStore(): ?string | setStore(?string store): void |
| `storeDetails` | [`?Store11`](../../doc/models/store-11.md) | Optional | The store that the terminal is assigned to. | getStoreDetails(): ?Store11 | setStoreDetails(?Store11 storeDetails): void |
| `terminal` | `string` | Required | The unique terminal ID. | getTerminal(): string | setTerminal(string terminal): void |
| `terminalStatus` | [`?string(TerminalStatusEnum)`](../../doc/models/terminal-status-enum.md) | Optional | The status of the terminal:<br><br>- `OnlineToday`, `OnlineLast1Day`, `OnlineLast2Days` etcetera to `OnlineLast7Days`: Indicates when in the past week the terminal was last online.<br><br>- `SwitchedOff`: Indicates it was more than a week ago that the terminal was last online.<br><br>- `ReAssignToInventoryPending`, `ReAssignToStorePending`, `ReAssignToMerchantInventoryPending`: Indicates the terminal is scheduled to be reassigned. | getTerminalStatus(): ?string | setTerminalStatus(?string terminalStatus): void |
| `wifiIp` | `?string` | Optional | The terminal's IP address in your Wi-Fi network. | getWifiIp(): ?string | setWifiIp(?string wifiIp): void |
| `wifiMac` | `?string` | Optional | The terminal's MAC address in your Wi-Fi network. | getWifiMac(): ?string | setWifiMac(?string wifiMac): void |

## Example

```php
use AdyenLib\Models\Builders\GetTerminalDetailsResponseBuilder;

$getTerminalDetailsResponse = GetTerminalDetailsResponseBuilder::init(
    'companyAccount0',
    'terminal4'
)
    ->bluetoothIp('bluetoothIp2')
    ->bluetoothMac('bluetoothMac6')
    ->country('country0')
    ->deviceModel('deviceModel4')
    ->dhcpEnabled(false)
    ->build();
```

