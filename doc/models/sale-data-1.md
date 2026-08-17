
# Sale Data 1

Data related to the Sale System.

## Structure

`SaleData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `operatorID` | `?string` | Optional | Identification of the Cashier or Operator.<br><br>**Constraints**: *Pattern*: `^.+$` | getOperatorID(): ?string | setOperatorID(?string operatorID): void |
| `operatorLanguage` | `?string` | Optional | Language of the Cashier or Operator.<br>If different from the Login.<br><br>**Constraints**: *Pattern*: `^[a-z]{2,2}$` | getOperatorLanguage(): ?string | setOperatorLanguage(?string operatorLanguage): void |
| `shiftNumber` | `?string` | Optional | Shift number.<br>If different from the Login, see Login SaleData.<br><br>**Constraints**: *Pattern*: `^.+$` | getShiftNumber(): ?string | setShiftNumber(?string shiftNumber): void |
| `saleTransactionID` | [`TransactionIDType1`](../../doc/models/transaction-id-type-1.md) | Required | Identification of a Sale transaction. | getSaleTransactionID(): TransactionIDType1 | setSaleTransactionID(TransactionIDType1 saleTransactionID): void |
| `saleReferenceID` | `?string` | Optional | Identification of a Sale global transaction for a sequence of related POI transactions.<br>If payment reservation.<br><br>**Constraints**: *Pattern*: `^.+$` | getSaleReferenceID(): ?string | setSaleReferenceID(?string saleReferenceID): void |
| `saleTerminalData` | [`?SaleTerminalData1`](../../doc/models/sale-terminal-data-1.md) | Optional | Information related to the software and hardware features of the Sale Terminal.<br>If content is not empty. | getSaleTerminalData(): ?SaleTerminalData1 | setSaleTerminalData(?SaleTerminalData1 saleTerminalData): void |
| `tokenRequestedType` | [`?string(TokenRequestedType1Enum)`](../../doc/models/token-requested-type-1-enum.md) | Optional | Type of token replacing the PAN of a payment card to identify the payment<br>mean of the customer. It allows, for a merchant, to use a token for a transaction<br>only or for a longer period.<br>Possible values:<br><br>* **Customer**<br>* **Transaction** | getTokenRequestedType(): ?string | setTokenRequestedType(?string tokenRequestedType): void |
| `customerOrderID` | `?string` | Optional | Additional and optional identification of a customer order.<br><br>**Constraints**: *Pattern*: `^.+$` | getCustomerOrderID(): ?string | setCustomerOrderID(?string customerOrderID): void |
| `customerOrderReq` | [`?(string(CustomerOrderReqEnum)[])`](../../doc/models/customer-order-req-enum.md) | Optional | List of customer order open, closed or both to be sent in the response messages.<br>Possible values:<br><br>* **Both**<br>* **Closed**<br>* **Open** | getCustomerOrderReq(): ?array | setCustomerOrderReq(?array customerOrderReq): void |
| `saleToPOIData` | `?string` | Optional | Sale information intended for the POI.<br>Stored with the transaction.<br><br>**Constraints**: *Pattern*: `^.+$` | getSaleToPOIData(): ?string | setSaleToPOIData(?string saleToPOIData): void |
| `saleToAcquirerData` | `?string` | Optional | Sale information intended for the Acquirer.<br>Send to the Acquirer if present.<br><br>**Constraints**: *Pattern*: `^.+$` | getSaleToAcquirerData(): ?string | setSaleToAcquirerData(?string saleToAcquirerData): void |
| `saleToIssuerData` | [`?SaleToIssuerData1`](../../doc/models/sale-to-issuer-data-1.md) | Optional | Sale information intended for the Issuer.<br>Send to the Acquirer if present. | getSaleToIssuerData(): ?SaleToIssuerData1 | setSaleToIssuerData(?SaleToIssuerData1 saleToIssuerData): void |

## Example

```php
use AdyenLib\Models\Builders\SaleData1Builder;
use AdyenLib\Models\Builders\TransactionIDType1Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\SaleTerminalData1Builder;

$saleData1 = SaleData1Builder::init(
    TransactionIDType1Builder::init(
        'TransactionID2',
        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
    )->build()
)
    ->operatorID('OperatorID6')
    ->operatorLanguage('OperatorLanguage0')
    ->shiftNumber('ShiftNumber8')
    ->saleReferenceID('SaleReferenceID0')
    ->saleTerminalData(
        SaleTerminalData1Builder::init()
            ->totalsGroupID('TotalsGroupID4')
            ->build()
    )
    ->build();
```

