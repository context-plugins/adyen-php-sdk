
# Get Totals Request

It conveys information from the Sale System related to the scope and the format of the totals to be computed by the POI System.
Content of the Get Totals Request message.

## Structure

`GetTotalsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalDetails` | [`?(string(TotalDetailEnum)[])`](../../doc/models/total-detail-enum.md) | Optional | Indicates the hierarchical structure of the reconciliation result of the Sale to POI reconciliation.<br>Required to present totals per value of element included in this cluster (POI Terminal, Sale Terminal, Cashier, Shift, TotalsGroupID).<br>Possible values:<br><br>* **OperatorID**<br>* **POIID**<br>* **SaleID**<br>* **ShiftNumber**<br>* **TotalsGroupID** | getTotalDetails(): ?array | setTotalDetails(?array totalDetails): void |
| `totalFilter` | [`?TotalFilter2`](../../doc/models/total-filter-2.md) | Optional | Filter to compute the totals.<br>Used for the Get Totals, to request totals for a (or a combination of) particular value of the POI Terminal, Sale Terminal, Cashier, Shift, or TotalsGroupID. | getTotalFilter(): ?TotalFilter2 | setTotalFilter(?TotalFilter2 totalFilter): void |

## Example

```php
use AdyenLib\Models\Builders\GetTotalsRequestBuilder;
use AdyenLib\Models\TotalDetailEnum;
use AdyenLib\Models\Builders\TotalFilter2Builder;

$getTotalsRequest = GetTotalsRequestBuilder::init()
    ->totalDetails(
        [
            TotalDetailEnum::POIID,
            TotalDetailEnum::TOTALSGROUPID,
            TotalDetailEnum::SHIFTNUMBER
        ]
    )
    ->totalFilter(
        TotalFilter2Builder::init()
            ->pOIID('POIID6')
            ->saleID('SaleID8')
            ->operatorID('OperatorID8')
            ->shiftNumber('ShiftNumber0')
            ->totalsGroupID('TotalsGroupID0')
            ->build()
    )
    ->build();
```

