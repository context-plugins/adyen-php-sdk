
# Encrypted Order Data 4

The order request object that contains a pspReference that represents the order and the matching encrypted order data.

## Structure

`EncryptedOrderData4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderData` | `string` | Required | The encrypted order data.<br><br>**Constraints**: *Maximum Length*: `5000` | getOrderData(): string | setOrderData(string orderData): void |
| `pspReference` | `string` | Required | The `pspReference` that belongs to the order. | getPspReference(): string | setPspReference(string pspReference): void |

## Example

```php
use AdyenLib\Models\Builders\EncryptedOrderData4Builder;

$encryptedOrderData4 = EncryptedOrderData4Builder::init(
    'orderData2',
    'pspReference2'
)->build();
```

