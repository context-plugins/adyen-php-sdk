
# Paginated Balance Accounts Response

## Structure

`PaginatedBalanceAccountsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAccounts` | [`BalanceAccountBase[]`](../../doc/models/balance-account-base.md) | Required | List of balance accounts. | getBalanceAccounts(): array | setBalanceAccounts(array balanceAccounts): void |
| `hasNext` | `bool` | Required | Indicates whether there are more items on the next page. | getHasNext(): bool | setHasNext(bool hasNext): void |
| `hasPrevious` | `bool` | Required | Indicates whether there are more items on the previous page. | getHasPrevious(): bool | setHasPrevious(bool hasPrevious): void |

## Example

```php
use AdyenLib\Models\Builders\PaginatedBalanceAccountsResponseBuilder;
use AdyenLib\Models\Builders\BalanceAccountBaseBuilder;
use AdyenLib\Models\Builders\PlatformPaymentConfiguration1Builder;
use AdyenLib\Utils\DateTimeHelper;

$paginatedBalanceAccountsResponse = PaginatedBalanceAccountsResponseBuilder::init(
    [
        BalanceAccountBaseBuilder::init(
            'accountHolderId0',
            'id8'
        )
            ->defaultCurrencyCode('defaultCurrencyCode2')
            ->description('description8')
            ->metadata(
                [
                    'key0' => 'metadata5',
                    'key1' => 'metadata6',
                    'key2' => 'metadata7'
                ]
            )
            ->platformPaymentConfiguration(
                PlatformPaymentConfiguration1Builder::init()
                    ->salesDayClosingTime(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                    ->settlementDelayDays(80)
                    ->build()
            )
            ->build()
    ],
    false,
    false
)->build();
```

