
# Account Detail Balance

## Structure

`AccountDetailBalance`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `?string` | Optional | The code of the account that holds the balance. | getAccountCode(): ?string | setAccountCode(?string accountCode): void |
| `detailBalance` | [`?DetailBalance3`](../../doc/models/detail-balance-3.md) | Optional | Details of the balance held by the account. | getDetailBalance(): ?DetailBalance3 | setDetailBalance(?DetailBalance3 detailBalance): void |

## Example

```php
use AdyenLib\Models\Builders\AccountDetailBalanceBuilder;
use AdyenLib\Models\Builders\DetailBalance3Builder;
use AdyenLib\Models\Builders\AmountBuilder;

$accountDetailBalance = AccountDetailBalanceBuilder::init()
    ->accountCode('accountCode6')
    ->detailBalance(
        DetailBalance3Builder::init()
            ->balance(
                [
                    AmountBuilder::init(
                        'currency4',
                        128
                    )->build(),
                    AmountBuilder::init(
                        'currency4',
                        128
                    )->build()
                ]
            )
            ->onHoldBalance(
                [
                    AmountBuilder::init(
                        'currency8',
                        72
                    )->build(),
                    AmountBuilder::init(
                        'currency8',
                        72
                    )->build(),
                    AmountBuilder::init(
                        'currency8',
                        72
                    )->build()
                ]
            )
            ->pendingBalance(
                [
                    AmountBuilder::init(
                        'currency2',
                        254
                    )->build()
                ]
            )->build()
    )->build();
```

