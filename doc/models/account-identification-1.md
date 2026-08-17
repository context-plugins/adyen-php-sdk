
# Account Identification 1

Contains the account number to which the payment funds are sent.

## Structure

`AccountIdentification1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\AccountIdentification1Builder;

$accountIdentification1 = AccountIdentification1Builder::init()
    ->type('AccountIdentification1')
    ->build();
```

