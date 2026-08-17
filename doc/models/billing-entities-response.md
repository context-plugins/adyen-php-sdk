
# Billing Entities Response

## Structure

`BillingEntitiesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(BillingEntity[])`](../../doc/models/billing-entity.md) | Optional | List of legal entities that can be used for the billing of orders. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\BillingEntitiesResponseBuilder;
use AdyenLib\Models\Builders\BillingEntityBuilder;
use AdyenLib\Models\Builders\Address11Builder;

$billingEntitiesResponse = BillingEntitiesResponseBuilder::init()
    ->data(
        [
            BillingEntityBuilder::init()
                ->address(
                    Address11Builder::init()
                        ->city('city6')
                        ->companyName('companyName8')
                        ->country('country0')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->build()
                )
                ->email('email6')
                ->id('id0')
                ->name('name0')
                ->taxId('taxId6')
                ->build(),
            BillingEntityBuilder::init()
                ->address(
                    Address11Builder::init()
                        ->city('city6')
                        ->companyName('companyName8')
                        ->country('country0')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->build()
                )
                ->email('email6')
                ->id('id0')
                ->name('name0')
                ->taxId('taxId6')
                ->build(),
            BillingEntityBuilder::init()
                ->address(
                    Address11Builder::init()
                        ->city('city6')
                        ->companyName('companyName8')
                        ->country('country0')
                        ->postalCode('postalCode8')
                        ->stateOrProvince('stateOrProvince4')
                        ->build()
                )
                ->email('email6')
                ->id('id0')
                ->name('name0')
                ->taxId('taxId6')
                ->build()
        ]
    )
    ->build();
```

