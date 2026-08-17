
# Bank Account Details 1

Contains the business account details. Returned when you create a payment instrument with `type` **bankAccount**.

## Structure

`BankAccountDetails1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `?string` | Optional | The bank account number, without separators or whitespace. | getAccountNumber(): ?string | setAccountNumber(?string accountNumber): void |
| `accountType` | `?string` | Optional | The bank account type.<br><br>Possible values: **checking** or **savings**. Defaults to **checking**.<br><br>**Default**: `'checking'` | getAccountType(): ?string | setAccountType(?string accountType): void |
| `branchNumber` | `?string` | Optional | The bank account branch number, without separators or whitespace | getBranchNumber(): ?string | setBranchNumber(?string branchNumber): void |
| `formFactor` | `?string` | Optional | Business accounts with a `formFactor` value of **physical** are business accounts issued under the central bank of that country. The default value is **physical** for NL, US, and UK business accounts.<br><br>Adyen creates a local IBAN for business accounts when the `formFactor` value is set to **virtual**. The local IBANs that are supported are for DE and FR, which reference a physical NL account, with funds being routed through the central bank of NL.<br><br>**Default**: `'physical'` | getFormFactor(): ?string | setFormFactor(?string formFactor): void |
| `iban` | `?string` | Optional | The international bank account number as defined in the [ISO-13616](https://www.iso.org/standard/81090.html) standard. | getIban(): ?string | setIban(?string iban): void |
| `routingNumber` | `?string` | Optional | The [routing number](https://en.wikipedia.org/wiki/ABA_routing_transit_number), without separators or whitespace. | getRoutingNumber(): ?string | setRoutingNumber(?string routingNumber): void |
| `sortCode` | `?string` | Optional | The [sort code](https://en.wikipedia.org/wiki/Sort_code), without separators or whitespace. | getSortCode(): ?string | setSortCode(?string sortCode): void |
| `type` | `string` | Required | **iban** or **usLocal** or **ukLocal**<br><br>**Default**: `'iban'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\BankAccountDetails1Builder;

$bankAccountDetails1 = BankAccountDetails1Builder::init(
    'iban'
)
    ->accountNumber('accountNumber4')
    ->accountType('checking')
    ->branchNumber('branchNumber8')
    ->formFactor('physical')
    ->iban('iban2')
    ->build();
```

