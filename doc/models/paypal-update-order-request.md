
# Paypal Update Order Request

## Structure

`PaypalUpdateOrderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`?Amount44`](../../doc/models/amount-44.md) | Optional | The updated final payment amount. This amount is the item total plus the shipping costs of the selected `deliveryMethod`. | getAmount(): ?Amount44 | setAmount(?Amount44 amount): void |
| `deliveryAddress` | [`?DeliveryAddress5`](../../doc/models/delivery-address-5.md) | Optional | The delivery address for this order. | getDeliveryAddress(): ?DeliveryAddress5 | setDeliveryAddress(?DeliveryAddress5 deliveryAddress): void |
| `deliveryMethods` | [`?(DeliveryMethod[])`](../../doc/models/delivery-method.md) | Optional | The list of new delivery methods and the cost of each. | getDeliveryMethods(): ?array | setDeliveryMethods(?array deliveryMethods): void |
| `discountAmount` | [`?Amount45`](../../doc/models/amount-45.md) | Optional | The discount amount for this order. | getDiscountAmount(): ?Amount45 | setDiscountAmount(?Amount45 discountAmount): void |
| `paymentData` | `?string` | Optional | The `paymentData` from the client side. This value changes every time you make a `/paypal/updateOrder` request. | getPaymentData(): ?string | setPaymentData(?string paymentData): void |
| `pspReference` | `?string` | Optional | The original `pspReference` from the `/payments` response. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `sessionId` | `?string` | Optional | The original `sessionId` from the `/sessions` response. | getSessionId(): ?string | setSessionId(?string sessionId): void |
| `shippingAmount` | [`?Amount46`](../../doc/models/amount-46.md) | Optional | The shipping amount for this order. | getShippingAmount(): ?Amount46 | setShippingAmount(?Amount46 shippingAmount): void |
| `taxTotal` | [`?TaxTotal2`](../../doc/models/tax-total-2.md) | Optional | Total tax amount from the order. | getTaxTotal(): ?TaxTotal2 | setTaxTotal(?TaxTotal2 taxTotal): void |

## Example

```php
use AdyenLib\Models\Builders\PaypalUpdateOrderRequestBuilder;
use AdyenLib\Models\Builders\Amount44Builder;
use AdyenLib\Models\Builders\DeliveryAddress5Builder;
use AdyenLib\Models\Builders\DeliveryMethodBuilder;
use AdyenLib\Models\Builders\Amount24Builder;
use AdyenLib\Models\Type21Enum;
use AdyenLib\Models\Builders\Amount45Builder;

$paypalUpdateOrderRequest = PaypalUpdateOrderRequestBuilder::init()
    ->amount(
        Amount44Builder::init(
            'currency2',
            110
        )->build()
    )
    ->deliveryAddress(
        DeliveryAddress5Builder::init(
            'city4',
            'country0',
            'houseNumberOrName4',
            'postalCode2',
            'street6'
        )
            ->firstName('firstName8')
            ->lastName('lastName0')
            ->stateOrProvince('stateOrProvince6')
            ->build()
    )
    ->deliveryMethods(
        [
            DeliveryMethodBuilder::init()
                ->amount(
                    Amount24Builder::init(
                        'currency2',
                        110
                    )->build()
                )
                ->description('description6')
                ->reference('reference2')
                ->selected(false)
                ->type(Type21Enum::SHIPPING)
                ->build(),
            DeliveryMethodBuilder::init()
                ->amount(
                    Amount24Builder::init(
                        'currency2',
                        110
                    )->build()
                )
                ->description('description6')
                ->reference('reference2')
                ->selected(false)
                ->type(Type21Enum::SHIPPING)
                ->build()
        ]
    )
    ->discountAmount(
        Amount45Builder::init(
            'currency8',
            168
        )->build()
    )
    ->paymentData('paymentData2')
    ->build();
```

