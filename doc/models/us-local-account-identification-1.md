
# US Local Account Identification 1

## Structure

`USLocalAccountIdentification1`

## Inherits From

[`BankAccountIdentification`](../../doc/models/bank-account-identification.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `18` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `accountType` | [`?string(AccountType2Enum)`](../../doc/models/account-type-2-enum.md) | Optional | The bank account type.<br><br>Possible values: **checking** or **savings**. Defaults to **checking**. | getAccountType(): ?string | setAccountType(?string accountType): void |
| `routingNumber` | `string` | Required | The 9-digit [routing number](https://en.wikipedia.org/wiki/ABA_routing_transit_number), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `9`, *Maximum Length*: `9` | getRoutingNumber(): string | setRoutingNumber(string routingNumber): void |

## Example

```php
use AdyenLib\Models\Builders\USLocalAccountIdentification1Builder;
use AdyenLib\Models\AccountType2Enum;

$uSLocalAccountIdentification1 = USLocalAccountIdentification1Builder::init(
    'accountNumber2',
    'routingNumber2'
)
    ->type('usLocal')
    ->accountType(AccountType2Enum::CHECKING)
    ->build();
```

