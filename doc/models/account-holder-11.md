
# Account Holder 11

Contains the full name of the person or entity that receives the payment funds).

## Structure

`AccountHolder11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fullName` | `string` | Required | Full name of the account holder.<br><br>**Constraints**: *Minimum Length*: `1` | getFullName(): string | setFullName(string fullName): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolder11Builder;

$accountHolder11 = AccountHolder11Builder::init(
    'John Doe'
)->build();
```

