
# Payment Acquirer Data

Data related to the response from the payment Acquirer.

## Structure

`PaymentAcquirerData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acquirerID` | `?int` | Optional | Identification of the Acquirer.<br>Identification of the Acquirer when the POI System is multi-acquirer. | getAcquirerID(): ?int | setAcquirerID(?int acquirerID): void |
| `merchantID` | `string` | Required | Identification of the Merchant for the Acquirer.<br><br>**Constraints**: *Pattern*: `^.+$` | getMerchantID(): string | setMerchantID(string merchantID): void |
| `acquirerPOIID` | `string` | Required | Identification of the POI for the payment Acquirer.<br><br>**Constraints**: *Pattern*: `^.+$` | getAcquirerPOIID(): string | setAcquirerPOIID(string acquirerPOIID): void |
| `acquirerTransactionID` | [`?TransactionIDType6`](../../doc/models/transaction-id-type-6.md) | Optional | Identification of the Transaction for the Acquirer.<br>If provided by the Acquirer. | getAcquirerTransactionID(): ?TransactionIDType6 | setAcquirerTransactionID(?TransactionIDType6 acquirerTransactionID): void |
| `approvalCode` | `?string` | Optional | Code assigned to a transaction approval by the Acquirer.<br>If available.<br><br>**Constraints**: *Pattern*: `^.+$` | getApprovalCode(): ?string | setApprovalCode(?string approvalCode): void |
| `hostReconciliationID` | `?string` | Optional | Identifier of a reconciliation period with a payment or loyalty host. Allows the assignment of a transaction to the Acquirer reconciliation (or batch).<br><br>**Constraints**: *Pattern*: `^.+$` | getHostReconciliationID(): ?string | setHostReconciliationID(?string hostReconciliationID): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentAcquirerDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType6Builder;
use AdyenLib\Utils\DateTimeHelper;

$paymentAcquirerData = PaymentAcquirerDataBuilder::init(
    'MerchantID0',
    'AcquirerPOIID0'
)
    ->acquirerID(46)
    ->acquirerTransactionID(
        TransactionIDType6Builder::init(
            'TransactionID2',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
    ->approvalCode('ApprovalCode4')
    ->hostReconciliationID('HostReconciliationID4')
    ->build();
```

