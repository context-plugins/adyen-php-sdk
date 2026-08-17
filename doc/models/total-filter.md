
# Total Filter

## Structure

`TotalFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pOIID` | `?string` | Optional | Identification of a POI System or a POI Terminal for the Sale to POI protocol.<br><br>**Constraints**: *Pattern*: `^.+$` | getPOIID(): ?string | setPOIID(?string pOIID): void |
| `saleID` | `?string` | Optional | Identification of a Sale System or a Sale Terminal for the Sale to POI protocol.<br><br>**Constraints**: *Pattern*: `^.+$` | getSaleID(): ?string | setSaleID(?string saleID): void |
| `operatorID` | `?string` | Optional | Identification of the Cashier or Operator.<br><br>**Constraints**: *Pattern*: `^.+$` | getOperatorID(): ?string | setOperatorID(?string operatorID): void |
| `shiftNumber` | `?string` | Optional | Shift number.<br><br>**Constraints**: *Pattern*: `^.+$` | getShiftNumber(): ?string | setShiftNumber(?string shiftNumber): void |
| `totalsGroupID` | `?string` | Optional | Sent if totals in the response have to be computed only for this particular value of TotalsGroupID.<br><br>**Constraints**: *Pattern*: `^.{1,16}$` | getTotalsGroupID(): ?string | setTotalsGroupID(?string totalsGroupID): void |

## Example

```php
use AdyenLib\Models\Builders\TotalFilterBuilder;

$totalFilter = TotalFilterBuilder::init()
    ->pOIID('POIID6')
    ->saleID('SaleID2')
    ->operatorID('OperatorID8')
    ->shiftNumber('ShiftNumber0')
    ->totalsGroupID('TotalsGroupID0')
    ->build();
```

