
# Sale Terminal Data 1

Information related to the software and hardware features of the Sale Terminal.
If content is not empty.

## Structure

`SaleTerminalData1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalsGroupID` | `?string` | Optional | Identification of a group of transactions on a POI Terminal, having the same Sale features.<br>Could be used to group POI for reconciliation or other purpose defined by the Sale System. The default value is assigned by the Login Request.<br><br>**Constraints**: *Pattern*: `^.{1,16}$` | getTotalsGroupID(): ?string | setTotalsGroupID(?string totalsGroupID): void |

## Example

```php
use AdyenLib\Models\Builders\SaleTerminalData1Builder;

$saleTerminalData1 = SaleTerminalData1Builder::init()
    ->totalsGroupID('TotalsGroupID6')
    ->build();
```

