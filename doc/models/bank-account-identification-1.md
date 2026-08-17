
# Bank Account Identification 1

Contains the identification information of the account to which you can transfer funds related to repayments.

## Structure

`BankAccountIdentification1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\BankAccountIdentification1Builder;

$bankAccountIdentification1 = BankAccountIdentification1Builder::init()
    ->type('BankAccountIdentification1')
    ->build();
```

