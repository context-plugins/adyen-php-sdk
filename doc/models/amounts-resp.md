
# Amounts Resp

## Structure

`AmountsResp`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `?string` | Optional | Currency of a monetary amount.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getCurrency(): ?string | setCurrency(?string currency): void |
| `authorizedAmount` | `float` | Required | Amount requested by the Sale for the payment.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getAuthorizedAmount(): float | setAuthorizedAmount(float authorizedAmount): void |
| `totalRebatesAmount` | `?float` | Optional | Sum of rebates in amount (total amount or line item amount) for all the loyalty programs.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getTotalRebatesAmount(): ?float | setTotalRebatesAmount(?float totalRebatesAmount): void |
| `totalFeesAmount` | `?float` | Optional | Total amount of financial fees.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getTotalFeesAmount(): ?float | setTotalFeesAmount(?float totalFeesAmount): void |
| `cashBackAmount` | `?float` | Optional | The cash-back part of the amount requested by the Sale for the payment.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getCashBackAmount(): ?float | setCashBackAmount(?float cashBackAmount): void |
| `tipAmount` | `?float` | Optional | Amount paid for a tip. Allow the printing of the tip on the receipt, and to qualify the tip part of the amount.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getTipAmount(): ?float | setTipAmount(?float tipAmount): void |

## Example

```php
use AdyenLib\Models\Builders\AmountsRespBuilder;

$amountsResp = AmountsRespBuilder::init(
    166.9
)
    ->currency('Currency2')
    ->totalRebatesAmount(86.42)
    ->totalFeesAmount(147.46)
    ->cashBackAmount(240.2)
    ->tipAmount(53.34)
    ->build();
```

