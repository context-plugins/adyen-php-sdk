
# Checkout Order Response

## Structure

`CheckoutOrderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount12`](../../doc/models/amount-12.md) | Optional | The initial amount of the order. | getAmount(): ?Amount12 | setAmount(?Amount12 amount): void |
| `expiresAt` | `?string` | Optional | The expiry date for the order. | getExpiresAt(): ?string | setExpiresAt(?string expiresAt): void |
| `orderData` | `?string` | Optional | The encrypted order data. | getOrderData(): ?string | setOrderData(?string orderData): void |
| `pspReference` | `string` | Required | The `pspReference` that belongs to the order. | getPspReference(): string | setPspReference(string pspReference): void |
| `reference` | `?string` | Optional | The merchant reference for the order. | getReference(): ?string | setReference(?string reference): void |
| `remainingAmount` | [`?Amount13`](../../doc/models/amount-13.md) | Optional | The updated remaining amount. | getRemainingAmount(): ?Amount13 | setRemainingAmount(?Amount13 remainingAmount): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutOrderResponseBuilder;
use AdyenLib\Models\Builders\Amount12Builder;
use AdyenLib\Models\Builders\Amount13Builder;

$checkoutOrderResponse = CheckoutOrderResponseBuilder::init(
    'pspReference8'
)
    ->amount(
        Amount12Builder::init(
            'currency2',
            110
        )->build()
    )
    ->expiresAt('expiresAt6')
    ->orderData('orderData8')
    ->reference('reference4')
    ->remainingAmount(
        Amount13Builder::init(
            'currency6',
            156
        )->build()
    )->build();
```

