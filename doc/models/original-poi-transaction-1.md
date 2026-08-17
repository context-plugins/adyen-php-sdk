
# Original POI Transaction 1

Identification of a previous POI transaction.
If StoredValueTransactionType is Reverse or Duplicate.

## Structure

`OriginalPOITransaction1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `saleID` | `?string` | Optional | Identification of a Sale System for the NEXO SaletoPOI protocol.<br><br>**Constraints**: *Pattern*: `^.+$` | getSaleID(): ?string | setSaleID(?string saleID): void |
| `pOIID` | `?string` | Optional | Identification of a payment terminal for the NEXO SaletoPOI protocol.<br>If original transaction is coming from another POI.<br><br>**Constraints**: *Pattern*: `^.+$` | getPOIID(): ?string | setPOIID(?string pOIID): void |
| `pOITransactionID` | [`?TransactionIDType4`](../../doc/models/transaction-id-type-4.md) | Optional | Unique identification of a POI transaction for a POI.<br>Absent if SaleReferenceID is sufficient to identify the transaction. | getPOITransactionID(): ?TransactionIDType4 | setPOITransactionID(?TransactionIDType4 pOITransactionID): void |
| `reuseCardDataFlag` | `?bool` | Optional | Indicates if the card data has to be retrieved from a previous transaction.<br><br>**Default**: `true` | getReuseCardDataFlag(): ?bool | setReuseCardDataFlag(?bool reuseCardDataFlag): void |
| `approvalCode` | `?string` | Optional | Code assigned to a transaction approval by the Acquirer.<br>If referral.<br><br>**Constraints**: *Pattern*: `^.+$` | getApprovalCode(): ?string | setApprovalCode(?string approvalCode): void |
| `acquirerID` | `?int` | Optional | Identification of the Acquirer.<br>Restrict to the Acquirer if present. | getAcquirerID(): ?int | setAcquirerID(?int acquirerID): void |
| `amountValue` | `?float` | Optional | Value of an amount.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getAmountValue(): ?float | setAmountValue(?float amountValue): void |
| `hostTransactionID` | [`?TransactionIDType5`](../../doc/models/transaction-id-type-5.md) | Optional | Identification of the transaction by the host in charge of the stored value transaction.<br>If POITransactionID not present. | getHostTransactionID(): ?TransactionIDType5 | setHostTransactionID(?TransactionIDType5 hostTransactionID): void |

## Example

```php
use AdyenLib\Models\Builders\OriginalPOITransaction1Builder;
use AdyenLib\Models\Builders\TransactionIDType4Builder;
use AdyenLib\Utils\DateTimeHelper;

$originalPOITransaction1 = OriginalPOITransaction1Builder::init()
    ->saleID('SaleID4')
    ->pOIID('POIID8')
    ->pOITransactionID(
        TransactionIDType4Builder::init(
            'TransactionID2',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )
    ->reuseCardDataFlag(true)
    ->approvalCode('ApprovalCode2')
    ->build();
```

