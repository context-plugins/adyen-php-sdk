
# Payment Validations 2

The object that you can use to enable payment validations for a transaction.

## Structure

`PaymentValidations2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | [`?Name6`](../../doc/models/name-6.md) | Optional | - | getName(): ?Name6 | setName(?Name6 name): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentValidations2Builder;
use AdyenLib\Models\Builders\Name6Builder;

$paymentValidations2 = PaymentValidations2Builder::init()
    ->name(
        Name6Builder::init(
            'status2'
        )->build()
    )->build();
```

