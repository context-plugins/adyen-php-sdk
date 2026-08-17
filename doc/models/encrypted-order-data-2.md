
# Encrypted Order Data 2

The order information required for partial payments.

## Structure

`EncryptedOrderData2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderData` | `string` | Required | The encrypted order data.<br><br>**Constraints**: *Maximum Length*: `5000` | getOrderData(): string | setOrderData(string orderData): void |
| `pspReference` | `string` | Required | The `pspReference` that belongs to the order. | getPspReference(): string | setPspReference(string pspReference): void |

## Example

```php
use AdyenLib\Models\Builders\EncryptedOrderData2Builder;

$encryptedOrderData2 = EncryptedOrderData2Builder::init(
    'orderData0',
    'pspReference0'
)->build();
```

