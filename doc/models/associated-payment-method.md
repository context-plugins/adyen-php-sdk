
# Associated Payment Method

## Structure

`AssociatedPaymentMethod`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enabled` | `bool` | Required | Indicates whether the payment method is enabled (**true**) or disabled (**false**). | getEnabled(): bool | setEnabled(bool enabled): void |
| `id` | `string` | Required | The identifier of the payment method. | getId(): string | setId(string id): void |
| `type` | `string` | Required | Payment method [variant](https://docs.adyen.com/development-resources/paymentmethodvariant#management-api). | getType(): string | setType(string type): void |

## Example

```php
use AdyenLib\Models\Builders\AssociatedPaymentMethodBuilder;

$associatedPaymentMethod = AssociatedPaymentMethodBuilder::init(
    false,
    'id2',
    'type8'
)->build();
```

