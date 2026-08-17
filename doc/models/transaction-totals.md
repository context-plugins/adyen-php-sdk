
# Transaction Totals

If Result is Success, contains all the totals, classified as required by the Sale in the message request. At least, transaction totals are provided per Acquirer, Acquirer Settlement, and Card Brand.
Result of the Sale to POI Reconciliation processing.

## Structure

`TransactionTotals`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentInstrumentType` | [`string(PaymentInstrumentType11Enum)`](../../doc/models/payment-instrument-type-11-enum.md) | Required | Type of payment instrument.<br>Possible values:<br><br>* **Card**<br>* **Cash**<br>* **Check**<br>* **Mobile**<br>* **StoredValue** | getPaymentInstrumentType(): string | setPaymentInstrumentType(string paymentInstrumentType): void |
| `acquirerID` | `?int` | Optional | Identification of the Acquirer. | getAcquirerID(): ?int | setAcquirerID(?int acquirerID): void |
| `hostReconciliationID` | `?string` | Optional | Identifier of a reconciliation period with a payment or loyalty host.<br><br>**Constraints**: *Pattern*: `^.+$` | getHostReconciliationID(): ?string | setHostReconciliationID(?string hostReconciliationID): void |
| `cardBrand` | `?string` | Optional | Type of payment or loyalty card.<br>If configured to present totals per card brand, and Response.Result is Success.<br><br>**Constraints**: *Pattern*: `^.+$` | getCardBrand(): ?string | setCardBrand(?string cardBrand): void |
| `pOIID` | `?string` | Optional | Identification of a POI System or a POI Terminal for the Sale to POI protocol.<br>Sent if requested in the message request.<br><br>**Constraints**: *Pattern*: `^.+$` | getPOIID(): ?string | setPOIID(?string pOIID): void |
| `saleID` | `?string` | Optional | Identification of a Sale System or a Sale Terminal for the Sale to POI protocol.<br>Sent if requested in the message request.<br><br>**Constraints**: *Pattern*: `^.+$` | getSaleID(): ?string | setSaleID(?string saleID): void |
| `operatorID` | `?string` | Optional | Identification of the Cashier or Operator.<br>Sent if requested in the message request.<br><br>**Constraints**: *Pattern*: `^.+$` | getOperatorID(): ?string | setOperatorID(?string operatorID): void |
| `shiftNumber` | `?string` | Optional | Shift number.<br>Sent if requested in the message request.<br><br>**Constraints**: *Pattern*: `^.+$` | getShiftNumber(): ?string | setShiftNumber(?string shiftNumber): void |
| `totalsGroupID` | `?string` | Optional | Identification of a group of transaction on a POI Terminal, having the same Sale features.<br>Sent if requested in the message request.<br><br>**Constraints**: *Pattern*: `^.{1,16}$` | getTotalsGroupID(): ?string | setTotalsGroupID(?string totalsGroupID): void |
| `paymentCurrency` | `?string` | Optional | Currency of a monetary amount.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getPaymentCurrency(): ?string | setPaymentCurrency(?string paymentCurrency): void |
| `paymentTotals` | [`?(PaymentTotals[])`](../../doc/models/payment-totals.md) | Optional | Totals of the payment transaction during the reconciliation period.<br>If both `TransactionCount` and `TransactionAmount` are not equal to zero. | getPaymentTotals(): ?array | setPaymentTotals(?array paymentTotals): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionTotalsBuilder;
use AdyenLib\Models\PaymentInstrumentType11Enum;

$transactionTotals = TransactionTotalsBuilder::init(
    PaymentInstrumentType11Enum::CARD
)
    ->acquirerID(160)
    ->hostReconciliationID('HostReconciliationID6')
    ->cardBrand('CardBrand4')
    ->pOIID('POIID4')
    ->saleID('SaleID0')
    ->build();
```

