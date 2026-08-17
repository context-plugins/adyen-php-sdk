
# Checkout Order Response 1

Contains updated information regarding the order in case order information was provided in the request.

## Structure

`CheckoutOrderResponse1`

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
use AdyenLib\Models\Builders\CheckoutOrderResponse1Builder;
use AdyenLib\Models\Builders\Amount12Builder;
use AdyenLib\Models\Builders\Amount13Builder;

$checkoutOrderResponse1 = CheckoutOrderResponse1Builder::init(
    'pspReference0'
)
    ->amount(
        Amount12Builder::init(
            'currency2',
            110
        )->build()
    )
    ->expiresAt('expiresAt4')
    ->orderData('orderData0')
    ->reference('reference6')
    ->remainingAmount(
        Amount13Builder::init(
            'currency6',
            156
        )->build()
    )->build();
```

