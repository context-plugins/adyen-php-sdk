
# HU Local Account Identification

## Structure

`HULocalAccountIdentification`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountNumber` | `string` | Required | The 24-digit bank account number, without separators or whitespace.<br><br>**Constraints**: *Minimum Length*: `24`, *Maximum Length*: `24` | getAccountNumber(): string | setAccountNumber(string accountNumber): void |
| `type` | `string` | Required, Constant | **huLocal**<br><br>**Value**: `'huLocal'` | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\HULocalAccountIdentificationBuilder;

$hULocalAccountIdentification = HULocalAccountIdentificationBuilder::init(
    'accountNumber4'
)->build();
```

