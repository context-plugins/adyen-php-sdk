
# Fund Source 11

The person or entity funding the money.

## Structure

`FundSource11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | A map of name-value pairs for passing additional or industry-specific data. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `billingAddress` | [`?Address`](../../doc/models/address.md) | Optional | The address where to send the invoice. | getBillingAddress(): ?Address | setBillingAddress(?Address billingAddress): void |
| `card` | [`?Card`](../../doc/models/card.md) | Optional | Credit card data.<br><br>Optional if `shopperReference` and `selectedRecurringDetailReference` are provided. | getCard(): ?Card | setCard(?Card card): void |
| `shopperEmail` | `?string` | Optional | Email address of the person. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperName` | [`?Name`](../../doc/models/name.md) | Optional | Name of the person. | getShopperName(): ?Name | setShopperName(?Name shopperName): void |
| `telephoneNumber` | `?string` | Optional | Phone number of the person | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |

## Example

```php
use AdyenLib\Models\Builders\FundSource11Builder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\CardBuilder;
use AdyenLib\Models\Builders\NameBuilder;

$fundSource11 = FundSource11Builder::init()
    ->additionalData(
        [
            'key0' => 'additionalData0',
            'key1' => 'additionalData1',
            'key2' => 'additionalData2'
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
        CardBuilder::init()
            ->cvc('cvc0')
            ->expiryMonth('expiryMonth0')
            ->expiryYear('expiryYear0')
            ->holderName('holderName2')
            ->issueNumber('issueNumber8')
            ->build()
    )
    ->shopperEmail('shopperEmail6')
    ->shopperName(
        NameBuilder::init(
            'firstName2',
            'lastName6'
        )->build()
    )->build();
```

