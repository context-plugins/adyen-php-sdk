
# Reconciliation Request

Content of the Reconciliation Request message.
It conveys Information related to the Reconciliation requested by the Sale System.

## Structure

`ReconciliationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reconciliationType` | [`string(ReconciliationType1Enum)`](../../doc/models/reconciliation-type-1-enum.md) | Required | Type of Reconciliation requested by the Sale to the POI.<br>Possible values:<br><br>* **AcquirerReconciliation**<br>* **AcquirerSynchronisation**<br>* **PreviousReconciliation**<br>* **SaleReconciliation** | getReconciliationType(): string | setReconciliationType(string reconciliationType): void |
| `acquirerID` | `?(int[])` | Optional | Identification of the Acquirer.<br>Could be present only if ReconciliationType is AcquirerReconciliation or AcquirerSynchronisation. | getAcquirerID(): ?array | setAcquirerID(?array acquirerID): void |
| `pOIReconciliationID` | `?int` | Optional | Identification of the reconciliation period between Sale and POI.<br>Absent if ReconciliationType is not PreviousReconciliation. | getPOIReconciliationID(): ?int | setPOIReconciliationID(?int pOIReconciliationID): void |

## Example

```php
use AdyenLib\Models\Builders\ReconciliationRequestBuilder;
use AdyenLib\Models\ReconciliationType1Enum;

$reconciliationRequest = ReconciliationRequestBuilder::init(
    ReconciliationType1Enum::ACQUIRERRECONCILIATION
)
    ->acquirerID(
        [
            62,
            63,
            64
        ]
    )
    ->pOIReconciliationID(20)
    ->build();
```

