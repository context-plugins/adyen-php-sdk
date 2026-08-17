
# Total Filter 2

Filter to compute the totals.
Used for the Get Totals, to request totals for a (or a combination of) particular value of the POI Terminal, Sale Terminal, Cashier, Shift, or TotalsGroupID.

## Structure

`TotalFilter2`

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
use AdyenLib\Models\Builders\TotalFilter2Builder;

$totalFilter2 = TotalFilter2Builder::init()
    ->pOIID('POIID4')
    ->saleID('SaleID8')
    ->operatorID('OperatorID8')
    ->shiftNumber('ShiftNumber0')
    ->totalsGroupID('TotalsGroupID0')
    ->build();
```

