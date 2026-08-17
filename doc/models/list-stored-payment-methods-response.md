
# List Stored Payment Methods Response

## Structure

`ListStoredPaymentMethodsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `?string` | Optional | Your merchant account. | getMerchantAccount(): ?string | setMerchantAccount(?string merchantAccount): void |
| `shopperReference` | `?string` | Optional | Your reference to uniquely identify this shopper, for example user ID or account ID. Minimum length: 3 characters.<br><br>> Your reference must not include personally identifiable information (PII), for example name or email address. | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |
| `storedPaymentMethods` | [`?(StoredPaymentMethodResource[])`](../../doc/models/stored-payment-method-resource.md) | Optional | List of all stored payment methods. | getStoredPaymentMethods(): ?array | setStoredPaymentMethods(?array storedPaymentMethods): void |

## Example

```php
use AdyenLib\Models\Builders\ListStoredPaymentMethodsResponseBuilder;
use AdyenLib\Models\Builders\StoredPaymentMethodResourceBuilder;
use AdyenLib\Models\Builders\Address5Builder;

$listStoredPaymentMethodsResponse = ListStoredPaymentMethodsResponseBuilder::init()
    ->merchantAccount('merchantAccount0')
    ->shopperReference('shopperReference6')
    ->storedPaymentMethods(
        [
            StoredPaymentMethodResourceBuilder::init()
                ->alias('alias4')
                ->aliasType('aliasType6')
                ->billingAddress(
                    Address5Builder::init(
                        'city8',
                        'country6',
                        'houseNumberOrName0',
                        'postalCode6',
                        'street2'
                    )
                        ->stateOrProvince('stateOrProvince0')
                        ->build()
                )
                ->brand('brand6')
                ->cardBin('cardBin8')
                ->build(),
            StoredPaymentMethodResourceBuilder::init()
                ->alias('alias4')
                ->aliasType('aliasType6')
                ->billingAddress(
                    Address5Builder::init(
                        'city8',
                        'country6',
                        'houseNumberOrName0',
                        'postalCode6',
                        'street2'
                    )
                        ->stateOrProvince('stateOrProvince0')
                        ->build()
                )
                ->brand('brand6')
                ->cardBin('cardBin8')
                ->build()
        ]
    )
    ->build();
```

