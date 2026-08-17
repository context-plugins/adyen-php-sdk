
# Fund Origin

## Structure

`FundOrigin`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billingAddress` | [`?Address3`](../../doc/models/address-3.md) | Optional | The address where to send the invoice. | getBillingAddress(): ?Address3 | setBillingAddress(?Address3 billingAddress): void |
| `shopperEmail` | `?string` | Optional | The email address of the person funding the money. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperName` | [`?Name1`](../../doc/models/name-1.md) | Optional | The name of the person funding the money. | getShopperName(): ?Name1 | setShopperName(?Name1 shopperName): void |
| `telephoneNumber` | `?string` | Optional | The phone number of the person funding the money. | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |
| `walletIdentifier` | `?string` | Optional | The unique identifier of the wallet where the funds are coming from. | getWalletIdentifier(): ?string | setWalletIdentifier(?string walletIdentifier): void |

## Example

```php
use AdyenLib\Models\Builders\FundOriginBuilder;
use AdyenLib\Models\Builders\Address3Builder;
use AdyenLib\Models\Builders\Name1Builder;

$fundOrigin = FundOriginBuilder::init()
    ->billingAddress(
        Address3Builder::init(
            'city8',
            'country6',
            'houseNumberOrName0',
            'postalCode6',
            'street2'
        )
            ->stateOrProvince('stateOrProvince0')
            ->build()
    )
    ->shopperEmail('shopperEmail6')
    ->shopperName(
        Name1Builder::init(
            'firstName2',
            'lastName6'
        )->build()
    )
    ->telephoneNumber('telephoneNumber2')
    ->walletIdentifier('walletIdentifier4')
    ->build();
```

