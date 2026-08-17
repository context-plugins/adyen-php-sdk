
# Amounts Req

Various amounts related to the payment request from the Sale System.

## Structure

`AmountsReq`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | Currency of a monetary amount.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getCurrency(): string | setCurrency(string currency): void |
| `requestedAmount` | `float` | Required | Amount requested by the Sale for the payment.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getRequestedAmount(): float | setRequestedAmount(float requestedAmount): void |
| `cashBackAmount` | `?float` | Optional | The cash-back part of the amount requested by the Sale for the payment.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getCashBackAmount(): ?float | setCashBackAmount(?float cashBackAmount): void |
| `tipAmount` | `?float` | Optional | Amount paid for a tip. Allow the printing of the tip on the receipt, and to qualify the tip part of the amount.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getTipAmount(): ?float | setTipAmount(?float tipAmount): void |
| `paidAmount` | `?float` | Optional | Amount already paid in case of split payment. Depending on the context, a split payment is either a split amount, or a split basket (required by some payment means as fleet cards). The PaidAmount is present when the split payment is a split<br>of the amount. Split of the basket involves two Sale Transactions, and does not have to be recognised by<br>the POI.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getPaidAmount(): ?float | setPaidAmount(?float paidAmount): void |
| `minimumAmountToDeliver` | `?float` | Optional | Minimum amount the Sale System is allowed to deliver for this payment. For the OneTimeReservation, when the maximum amount is unknown, the Sale System indicates the minimum amount it allows.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getMinimumAmountToDeliver(): ?float | setMinimumAmountToDeliver(?float minimumAmountToDeliver): void |
| `maximumCashBackAmount` | `?float` | Optional | Maximum amount which could be requested for cash-back to the Sale System. Allows the Cashier<br>to limit the amount value of cash-back to deliver to the Customer.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getMaximumCashBackAmount(): ?float | setMaximumCashBackAmount(?float maximumCashBackAmount): void |
| `minimumSplitAmount` | `?float` | Optional | Minimum amount of a split, which could be requested by a Customer.Allows the Merchant to limit the number of split requested by the Customer.<br><br>**Constraints**: `>= 0`, `<= 99999999.999999` | getMinimumSplitAmount(): ?float | setMinimumSplitAmount(?float minimumSplitAmount): void |

## Example

```php
use AdyenLib\Models\Builders\AmountsReqBuilder;

$amountsReq = AmountsReqBuilder::init(
    'Currency2',
    174.2
)
    ->cashBackAmount(213.4)
    ->tipAmount(175.86)
    ->paidAmount(119.66)
    ->minimumAmountToDeliver(209.06)
    ->maximumCashBackAmount(98.86)
    ->build();
```

