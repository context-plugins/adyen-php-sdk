
# Validate Shopper Id Request

## Structure

`ValidateShopperIdRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `1000` | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `paymentMethod` | [`ShopperIdPaymentMethod1`](../../doc/models/shopper-id-payment-method-1.md) | Required | paymentMethod | getPaymentMethod(): ShopperIdPaymentMethod1 | setPaymentMethod(ShopperIdPaymentMethod1 paymentMethod): void |
| `shopperEmail` | `?string` | Optional | **Constraints**: *Minimum Length*: `0`, *Maximum Length*: `300` | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperIP` | `?string` | Optional | **Constraints**: *Minimum Length*: `0`, *Maximum Length*: `15` | getShopperIP(): ?string | setShopperIP(?string shopperIP): void |
| `shopperReference` | `?string` | Optional | **Constraints**: *Minimum Length*: `0`, *Maximum Length*: `256` | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\ValidateShopperIdRequestBuilder;
use AdyenLib\Models\Builders\ShopperIdPaymentMethod1Builder;

$validateShopperIdRequest = ValidateShopperIdRequestBuilder::init(
    'merchantAccount0',
    ShopperIdPaymentMethod1Builder::init()
        ->type('ShopperIdPaymentMethod1')
        ->build()
)
    ->shopperEmail('shopperEmail8')
    ->shopperIP('shopperIP6')
    ->shopperReference('shopperReference6')
    ->build();
```

