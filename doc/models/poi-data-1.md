
# POI Data 1

Data related to the POI System.

## Structure

`POIData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pOITransactionID` | [`TransactionIDType2`](../../doc/models/transaction-id-type-2.md) | Required | Unique identification of a POI transaction for a POI. | getPOITransactionID(): TransactionIDType2 | setPOITransactionID(TransactionIDType2 pOITransactionID): void |
| `pOIReconciliationID` | `?int` | Optional | Identification of the reconciliation period between Sale and POI.<br>If Result is Success. | getPOIReconciliationID(): ?int | setPOIReconciliationID(?int pOIReconciliationID): void |

## Example

```php
use AdyenLib\Models\Builders\POIData1Builder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Utils\DateTimeHelper;

$pOIData1 = POIData1Builder::init(
    TransactionIDType2Builder::init(
        'TransactionID2',
        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
    )->build()
)
    ->pOIReconciliationID(66)
    ->build();
```

