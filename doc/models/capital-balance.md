
# Capital Balance

An object containing the details of the existing grant., Contains information about the balances of the disbursement., Contains information about the balances of the grant.

## Structure

`CapitalBalance`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes). | getCurrency(): string | setCurrency(string currency): void |
| `fee` | `int` | Required | Fee amount. | getFee(): int | setFee(int fee): void |
| `principal` | `int` | Required | Principal amount. | getPrincipal(): int | setPrincipal(int principal): void |
| `total` | `int` | Required | Total amount. A sum of principal amount and fee amount. | getTotal(): int | setTotal(int total): void |

## Example

```php
use AdyenLib\Models\Builders\CapitalBalanceBuilder;

$capitalBalance = CapitalBalanceBuilder::init(
    'currency2',
    8,
    46,
    86
)->build();
```

