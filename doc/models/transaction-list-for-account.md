
# Transaction List for Account

## Structure

`TransactionListForAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `string` | Required | The account for which to retrieve the transactions. | getAccountCode(): string | setAccountCode(string accountCode): void |
| `page` | `int` | Required | The page of transactions to retrieve.<br>Each page lists fifty (50) transactions.  The most recent transactions are included on page 1. | getPage(): int | setPage(int page): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionListForAccountBuilder;

$transactionListForAccount = TransactionListForAccountBuilder::init(
    'accountCode4',
    76
)->build();
```

