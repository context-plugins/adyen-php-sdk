
# Donation Campaigns Request

## Structure

`DonationCampaignsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `currency` | `string` | Required | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes/). | getCurrency(): string | setCurrency(string currency): void |
| `locale` | `?string` | Optional | Locale on the shopper interaction device. | getLocale(): ?string | setLocale(?string locale): void |
| `merchantAccount` | `string` | Required | Your merchant account identifier. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `store` | `?string` | Optional | Required for Adyen for Platforms integrations if you are a platform model. This is your [reference](https://docs.adyen.com/api-explorer/Management/3/post/merchants/(merchantId)/stores#request-reference) (on [balance platform](https://docs.adyen.com/platforms)) or the [storeReference](https://docs.adyen.com/api-explorer/Account/latest/post/updateAccountHolder#request-accountHolderDetails-storeDetails-storeReference) (in the [classic integration](https://docs.adyen.com/classic-platforms/processing-payments/route-payment-to-store/#route-a-payment-to-a-store)) for the ecommerce or point-of-sale store that is processing the payment. | getStore(): ?string | setStore(?string store): void |

## Example

```php
use AdyenLib\Models\Builders\DonationCampaignsRequestBuilder;

$donationCampaignsRequest = DonationCampaignsRequestBuilder::init(
    'currency8',
    'merchantAccount0'
)
    ->locale('locale6')
    ->store('store2')
    ->build();
```

