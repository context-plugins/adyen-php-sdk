
# POI Data 4

Data related to the POI System.
If Result is Success.

## Structure

`POIData4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pOITransactionID` | [`TransactionIDType2`](../../doc/models/transaction-id-type-2.md) | Required | Unique identification of a POI transaction for a POI. | getPOITransactionID(): TransactionIDType2 | setPOITransactionID(TransactionIDType2 pOITransactionID): void |
| `pOIReconciliationID` | `?int` | Optional | Identification of the reconciliation period between Sale and POI.<br>If Result is Success. | getPOIReconciliationID(): ?int | setPOIReconciliationID(?int pOIReconciliationID): void |

## Example

```php
use AdyenLib\Models\Builders\POIData4Builder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Utils\DateTimeHelper;

$pOIData4 = POIData4Builder::init(
    TransactionIDType2Builder::init(
        'TransactionID2',
        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
    )->build()
)
    ->pOIReconciliationID(148)
    ->build();
```

