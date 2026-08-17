
# US Local Account Identification

## Structure

`USLocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `18` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `accountType` | [`?string(AccountType2Enum)`](../../doc/models/account-type-2-enum.md) | Optional | The bank account type.<br><br>Possible values: **checking** or **savings**. Defaults to **checking**.<br><br>**Default**: `AccountType2Enum::CHECKING` | getAccountType(): ?string | setAccountType(?string accountType): void |
| `routingNumber` | `string` | Required | The 9-digit [routing number](https://en.wikipedia.org/wiki/ABA_routing_transit_number), without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `9`, *Maximum Length*: `9` | getRoutingNumber(): string | setRoutingNumber(string routingNumber): void |
| `type` | `string` | Required, Constant | **usLocal**<br><br>**Value**: `'usLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\USLocalAccountIdentificationBuilder;
use AdyenLib\Models\AccountType2Enum;

$uSLocalAccountIdentification = USLocalAccountIdentificationBuilder::init(
    'accountNumber4',
    'routingNumber8'
)
    ->accountType(AccountType2Enum::CHECKING)
    ->build();
```

