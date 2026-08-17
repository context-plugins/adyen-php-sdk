
# Fund Destination

## Structure

`FundDestination`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `iBAN` | `?string` | Optional | Bank Account Number of the recipient | getIBAN(): ?string | setIBAN(?string iBAN): void |
| `additionalData` | `?array<string,string>` | Optional | a map of name/value pairs for passing in additional/industry-specific data | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `billingAddress` | [`?Address`](../../doc/models/address.md) | Optional | The address where to send the invoice. | getBillingAddress(): ?Address | setBillingAddress(?Address billingAddress): void |
| `card` | [`?Card1`](../../doc/models/card-1.md) | Optional | Credit card data.<br><br>Optional if `shopperReference` and `selectedRecurringDetailReference` are provided. | getCard(): ?Card1 | setCard(?Card1 card): void |
| `selectedRecurringDetailReference` | `?string` | Optional | The `recurringDetailReference` you want to use for this payment. The value `LATEST` can be used to select the most recently stored recurring detail. | getSelectedRecurringDetailReference(): ?string | setSelectedRecurringDetailReference(?string selectedRecurringDetailReference): void |
| `shopperEmail` | `?string` | Optional | the email address of the person | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperName` | [`?Name`](../../doc/models/name.md) | Optional | the name of the person | getShopperName(): ?Name | setShopperName(?Name shopperName): void |
| `shopperReference` | `?string` | Optional | Required for recurring payments.<br>Your reference to uniquely identify this shopper, for example user ID or account ID. The value is case-sensitive and must be at least three characters.<br><br>> Your reference must not include personally identifiable information (PII) such as name or email address. | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |
| `subMerchant` | [`?SubMerchant`](../../doc/models/sub-merchant.md) | Optional | Required for Back-to-Back/ purchase driven load in Wallet transactions.<br>Contains the final merchant who will be receiving the money, also known as subMerchant, information. | getSubMerchant(): ?SubMerchant | setSubMerchant(?SubMerchant subMerchant): void |
| `telephoneNumber` | `?string` | Optional | the telephone number of the person | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |
| `walletPurpose` | `?string` | Optional | The purpose of a digital wallet transaction. | getWalletPurpose(): ?string | setWalletPurpose(?string walletPurpose): void |

## Example

```php
use AdyenLib\Models\Builders\FundDestinationBuilder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\Card1Builder;

$fundDestination = FundDestinationBuilder::init()
    ->iBAN('IBAN2')
    ->additionalData(
        [
            'key0' => 'additionalData8',
            'key1' => 'additionalData9',
            'key2' => 'additionalData0'
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
    ->selectedRecurringDetailReference('selectedRecurringDetailReference2')
    ->build();
```

