
# POI Data

Data related to the POI System.
In the Message Response, identification of the POI transaction.

## Structure

`POIData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pOITransactionID` | [`TransactionIDType2`](../../doc/models/transaction-id-type-2.md) | Required | Unique identification of a POI transaction for a POI. | getPOITransactionID(): TransactionIDType2 | setPOITransactionID(TransactionIDType2 pOITransactionID): void |
| `pOIReconciliationID` | `?int` | Optional | Identification of the reconciliation period between Sale and POI.<br>If Result is Success. | getPOIReconciliationID(): ?int | setPOIReconciliationID(?int pOIReconciliationID): void |

## Example

```php
use AdyenLib\Models\Builders\POIDataBuilder;
use AdyenLib\Models\Builders\TransactionIDType2Builder;
use AdyenLib\Utils\DateTimeHelper;

$pOIData = POIDataBuilder::init(
    TransactionIDType2Builder::init(
        'TransactionID2',
        DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
    )->build()
)
    ->pOIReconciliationID(208)
    ->build();
```

