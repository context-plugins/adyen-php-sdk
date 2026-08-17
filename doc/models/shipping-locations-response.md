
# Shipping Locations Response

## Structure

`ShippingLocationsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(ShippingLocation[])`](../../doc/models/shipping-location.md) | Optional | Physical locations where orders can be shipped to. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\ShippingLocationsResponseBuilder;
use AdyenLib\Models\Builders\ShippingLocationBuilder;
use AdyenLib\Models\Builders\Address21Builder;
use AdyenLib\Models\Builders\Contact1Builder;

$shippingLocationsResponse = ShippingLocationsResponseBuilder::init()
    ->data(
        [
            ShippingLocationBuilder::init()
                ->address(
                    Address21Builder::init()
                        ->city('city6')
                        ->companyName('companyName8')
                        ->country('country0')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->build()
                )
                ->contact(
                    Contact1Builder::init()
                        ->email('email4')
                        ->firstName('firstName2')
                        ->infix('infix6')
                        ->lastName('lastName6')
                        ->phoneNumber('phoneNumber2')
                        ->build()
                )
                ->id('id0')
                ->name('name0')
                ->build(),
            ShippingLocationBuilder::init()
                ->address(
                    Address21Builder::init()
                        ->city('city6')
                        ->companyName('companyName8')
                        ->country('country0')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->build()
                )
                ->contact(
                    Contact1Builder::init()
                        ->email('email4')
                        ->firstName('firstName2')
                        ->infix('infix6')
                        ->lastName('lastName6')
                        ->phoneNumber('phoneNumber2')
                        ->build()
                )
                ->id('id0')
                ->name('name0')
                ->build(),
            ShippingLocationBuilder::init()
                ->address(
                    Address21Builder::init()
                        ->city('city6')
                        ->companyName('companyName8')
                        ->country('country0')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->build()
                )
                ->contact(
                    Contact1Builder::init()
                        ->email('email4')
                        ->firstName('firstName2')
                        ->infix('infix6')
                        ->lastName('lastName6')
                        ->phoneNumber('phoneNumber2')
                        ->build()
                )
                ->id('id0')
                ->name('name0')
                ->build()
        ]
    )
    ->build();
```

