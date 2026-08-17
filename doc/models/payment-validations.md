
# Payment Validations

## Structure

`PaymentValidations`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | [`?Name6`](../../doc/models/name-6.md) | Optional | - | getName(): ?Name6 | setName(?Name6 name): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentValidationsBuilder;
use AdyenLib\Models\Builders\Name6Builder;

$paymentValidations = PaymentValidationsBuilder::init()
    ->name(
        Name6Builder::init(
            'status2'
        )->build()
    )->build();
```

