
# Account Holder 1

## Structure

`AccountHolder1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fullName` | `string` | Required | Full name of the account holder.<br><br>**Constraints**: *Minimum Length*: `1` | getFullName(): string | setFullName(string fullName): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolder1Builder;

$accountHolder1 = AccountHolder1Builder::init(
    'John Doe'
)->build();
```

