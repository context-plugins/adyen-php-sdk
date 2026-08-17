
# Balance Transfer Type 2 Enum

The type of balance transfer. Possible values: **tax**, **fee**, **terminalSale**, **credit**, **debit**, and **adjustment**.

## Enumeration

`BalanceTransferType2Enum`

## Fields

| Name |
|  --- |
| `TAX` |
| `FEE` |
| `TERMINALSALE` |
| `CREDIT` |
| `DEBIT` |
| `ADJUSTMENT` |

## Example

```php
use AdyenLib\Models\BalanceTransferType2Enum;

$balanceTransferType2 = BalanceTransferType2Enum::DEBIT;
```

