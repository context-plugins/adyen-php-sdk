
# Login Request

It conveys information related to the session (period between a Login and the following Logout) to process.
Content of the `LoginRequest` message.

## Structure

`LoginRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateTime` | `DateTime` | Required | Date and Time. In the Login request message, the Sale System gives its date and time to the POI System. In the Login response, the POI System gives its date and time to the Sale System. | getDateTime(): \DateTime | setDateTime(\DateTime dateTime): void |
| `saleSoftware` | [`SaleSoftware1`](../../doc/models/sale-software-1.md) | Required | Information related to the software of the Sale System which manages the Sale to POI protocol. | getSaleSoftware(): SaleSoftware1 | setSaleSoftware(SaleSoftware1 saleSoftware): void |
| `saleTerminalData` | [`?SaleTerminalData2`](../../doc/models/sale-terminal-data-2.md) | Optional | Information related to the software and hardware feature of the Sale Terminal.<br>Present if the login involve a Sale Terminal. | getSaleTerminalData(): ?SaleTerminalData2 | setSaleTerminalData(?SaleTerminalData2 saleTerminalData): void |
| `trainingModeFlag` | `?bool` | Optional | Training mode.<br>This flag indicates to the POI that the entire session will be not used to make real transaction, but is used for test of system or operator training.<br><br>**Default**: `false` | getTrainingModeFlag(): ?bool | setTrainingModeFlag(?bool trainingModeFlag): void |
| `operatorLanguage` | `string` | Required | Language of the Cashier or Operator.<br>Default value for Device type displays.<br><br>**Constraints**: *Pattern*: `^[a-z]{2,2}$` | getOperatorLanguage(): string | setOperatorLanguage(string operatorLanguage): void |
| `operatorID` | `?string` | Optional | Identification of the Cashier or Operator.<br>Four conditions to send it:<br><br>* The Sale System wants the POI to log it in the transaction log.<br>* Because of reconciliation with total on OperatorID.<br>* Because the POI needs it.<br>* Acquirer or issuer need it.<br><br>**Constraints**: *Pattern*: `^.+$` | getOperatorID(): ?string | setOperatorID(?string operatorID): void |
| `shiftNumber` | `?string` | Optional | Shift number.<br>Same as OperatorID.<br><br>**Constraints**: *Pattern*: `^.+$` | getShiftNumber(): ?string | setShiftNumber(?string shiftNumber): void |
| `tokenRequestedType` | [`?string(TokenRequestedType1Enum)`](../../doc/models/token-requested-type-1-enum.md) | Optional | Type of token replacing the PAN of a payment card to identify the payment<br>mean of the customer. It allows, for a merchant, to use a token for a transaction<br>only or for a longer period.<br>Possible values:<br><br>* **Customer**<br>* **Transaction** | getTokenRequestedType(): ?string | setTokenRequestedType(?string tokenRequestedType): void |
| `customerOrderReq` | [`?(string(CustomerOrderReqEnum)[])`](../../doc/models/customer-order-req-enum.md) | Optional | List of customer order open, closed or both to be sent in the response messages.<br>Possible values:<br><br>* **Both**<br>* **Closed**<br>* **Open** | getCustomerOrderReq(): ?array | setCustomerOrderReq(?array customerOrderReq): void |
| `pOISerialNumber` | `?string` | Optional | Serial number of a POI Terminal.<br>If the login involve a POI Terminal and not the first Login to the POI System.<br><br>**Constraints**: *Pattern*: `^.+$` | getPOISerialNumber(): ?string | setPOISerialNumber(?string pOISerialNumber): void |

## Example

```php
use AdyenLib\Models\Builders\LoginRequestBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleSoftware1Builder;
use AdyenLib\Models\Builders\SaleTerminalData2Builder;
use AdyenLib\Models\TokenRequestedType1Enum;

$loginRequest = LoginRequestBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    SaleSoftware1Builder::init(
        'ManufacturerID4',
        'ApplicationName8',
        'SoftwareVersion0',
        'CertificationCode4'
    )->build(),
    'OperatorLanguage0'
)
    ->saleTerminalData(
        SaleTerminalData2Builder::init()
            ->totalsGroupID('TotalsGroupID4')
            ->build()
    )
    ->trainingModeFlag(false)
    ->operatorID('OperatorID6')
    ->shiftNumber('ShiftNumber8')
    ->tokenRequestedType(TokenRequestedType1Enum::TRANSACTION)
    ->build();
```

