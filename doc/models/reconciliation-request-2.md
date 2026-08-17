
# Reconciliation Request 2

Content of the Reconciliation Request message.

## Structure

`ReconciliationRequest2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reconciliationType` | [`string(ReconciliationType1Enum)`](../../doc/models/reconciliation-type-1-enum.md) | Required | Type of Reconciliation requested by the Sale to the POI.<br>Possible values:<br><br>* **AcquirerReconciliation**<br>* **AcquirerSynchronisation**<br>* **PreviousReconciliation**<br>* **SaleReconciliation** | getReconciliationType(): string | setReconciliationType(string reconciliationType): void |
| `acquirerID` | `?(int[])` | Optional | Identification of the Acquirer.<br>Could be present only if ReconciliationType is AcquirerReconciliation or AcquirerSynchronisation. | getAcquirerID(): ?array | setAcquirerID(?array acquirerID): void |
| `pOIReconciliationID` | `?int` | Optional | Identification of the reconciliation period between Sale and POI.<br>Absent if ReconciliationType is not PreviousReconciliation. | getPOIReconciliationID(): ?int | setPOIReconciliationID(?int pOIReconciliationID): void |

## Example

```php
use AdyenLib\Models\Builders\ReconciliationRequest2Builder;
use AdyenLib\Models\ReconciliationType1Enum;

$reconciliationRequest2 = ReconciliationRequest2Builder::init(
    ReconciliationType1Enum::ACQUIRERRECONCILIATION
)
    ->acquirerID(
        [
            122,
            123,
            124
        ]
    )
    ->pOIReconciliationID(80)
    ->build();
```

