
# Sale Terminal Data 2

Information related to the software and hardware feature of the Sale Terminal.
Present if the login involve a Sale Terminal.

## Structure

`SaleTerminalData2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalsGroupID` | `?string` | Optional | Identification of a group of transactions on a POI Terminal, having the same Sale features.<br>Could be used to group POI for reconciliation or other purpose defined by the Sale System. The default value is assigned by the Login Request.<br><br>**Constraints**: *Pattern*: `^.{1,16}$` | getTotalsGroupID(): ?string | setTotalsGroupID(?string totalsGroupID): void |

## Example

```php
use AdyenLib\Models\Builders\SaleTerminalData2Builder;

$saleTerminalData2 = SaleTerminalData2Builder::init()
    ->totalsGroupID('TotalsGroupID4')
    ->build();
```

