
# Merchant Balance

## Structure

`MerchantBalance`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `availableFund` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | - | getAvailableFund(): ?Amount17 | setAvailableFund(?Amount17 availableFund): void |
| `deposit` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | - | getDeposit(): ?Amount17 | setDeposit(?Amount17 deposit): void |
| `merchantAccount` | `?string` | Optional | - | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |
| `nextPayout` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | - | getNextPayout(): ?Amount17 | setNextPayout(?Amount17 nextPayout): void |
| `pendingBalance` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | - | getPendingBalance(): ?Amount17 | setPendingBalance(?Amount17 pendingBalance): void |
| `reserve` | [`?Amount17`](../../doc/models/amount-17.md) | Optional | - | getReserve(): ?Amount17 | setReserve(?Amount17 reserve): void |

## Example

```php
use AdyenLib\Models\Builders\MerchantBalanceBuilder;
use AdyenLib\Models\Builders\Amount17Builder;

$merchantBalance = MerchantBalanceBuilder::init()
    ->availableFund(
        Amount17Builder::init(
            'currency4',
            152
        )->build()
    )
    ->deposit(
        Amount17Builder::init(
            'currency4',
            62
        )->build()
    )
    ->merchantAccount('merchantAccount6')
    ->nextPayout(
        Amount17Builder::init(
            'currency4',
            240
        )->build()
    )
    ->pendingBalance(
        Amount17Builder::init(
            'currency2',
            254
        )->build()
    )->build();
```

