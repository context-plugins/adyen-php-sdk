
# Name 6

## Structure

`Name6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `string` | Required | Set to **requested** to request a [name validation](https://docs.adyen.com/payment-methods/cards/name-validation) to verify if the cardholder name provided by the shopper matches the cardholder name on file at the issuing bank. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\Name6Builder;

$name6 = Name6Builder::init(
    'status2'
)->build();
```

