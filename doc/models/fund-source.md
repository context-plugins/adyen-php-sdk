
# Fund Source

## Structure

`FundSource`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | A map of name-value pairs for passing additional or industry-specific data. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `billingAddress` | [`?Address`](../../doc/models/address.md) | Optional | The address where to send the invoice. | getBillingAddress(): ?Address | setBillingAddress(?Address billingAddress): void |
| `card` | [`?Card1`](../../doc/models/card-1.md) | Optional | Credit card data.<br><br>Optional if `shopperReference` and `selectedRecurringDetailReference` are provided. | getCard(): ?Card1 | setCard(?Card1 card): void |
| `shopperEmail` | `?string` | Optional | Email address of the person. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperName` | [`?Name`](../../doc/models/name.md) | Optional | Name of the person. | getShopperName(): ?Name | setShopperName(?Name shopperName): void |
| `telephoneNumber` | `?string` | Optional | Phone number of the person | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |

## Example

```php
use AdyenLib\Models\Builders\FundSourceBuilder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\Card1Builder;
use AdyenLib\Models\Builders\NameBuilder;

$fundSource = FundSourceBuilder::init()
    ->additionalData(
        [
            'key0' => 'additionalData8'
        ]
    )
    ->billingAddress(
        AddressBuilder::init(
            'city8',
            'country6',
            'houseNumberOrName0',
            'postalCode6',
            'street2'
        )
            ->stateOrProvince('stateOrProvince0')
            ->build()
    )
    ->card(
        Card1Builder::init()
            ->cvc('cvc0')
            ->expiryMonth('expiryMonth0')
            ->expiryYear('expiryYear0')
            ->holderName('holderName2')
            ->issueNumber('issueNumber8')
            ->build()
    )
    ->shopperEmail('shopperEmail4')
    ->shopperName(
        NameBuilder::init(
            'firstName2',
            'lastName6'
        )->build()
    )->build();
```

