
# Payment Methods Request

## Structure

`PaymentMethodsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular payment request.<br><br>The `additionalData` object consists of entries, each of which includes the key and value. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `allowedPaymentMethods` | `?(string[])` | Optional | List of payment methods to be presented to the shopper. To refer to payment methods, use their [payment method type](https://docs.adyen.com/payment-methods/payment-method-types).<br><br>Example: `"allowedPaymentMethods":["ideal","applepay"]` | getAllowedPaymentMethods(): ?array | setAllowedPaymentMethods(?array allowedPaymentMethods): void |
| `amount` | [`?Amount2`](../../doc/models/amount-2.md) | Optional | The amount information for the transaction (in [minor units](https://docs.adyen.com/development-resources/currency-codes)). For [BIN or card verification](https://docs.adyen.com/payment-methods/cards/bin-data-and-card-verification) requests, set amount to 0 (zero). | getAmount(): ?Amount2 | setAmount(?Amount2 amount): void |
| `blockedPaymentMethods` | `?(string[])` | Optional | List of payment methods to be hidden from the shopper. To refer to payment methods, use their [payment method type](https://docs.adyen.com/payment-methods/payment-method-types).<br><br>Example: `"blockedPaymentMethods":["ideal","applepay"]` | getBlockedPaymentMethods(): ?array | setBlockedPaymentMethods(?array blockedPaymentMethods): void |
| `browserInfo` | [`?BrowserInfo`](../../doc/models/browser-info.md) | Optional | The shopper's browser information.<br><br>> For 3D Secure, the full object is required for web integrations. For mobile app integrations, include the `userAgent` and `acceptHeader` fields to indicate  that your integration can support a redirect in case a payment is routed to 3D Secure 2 redirect. | getBrowserInfo(): ?BrowserInfo | setBrowserInfo(?BrowserInfo browserInfo): void |
| `channel` | [`?string(Channel3Enum)`](../../doc/models/channel-3-enum.md) | Optional | The platform where a payment transaction takes place. This field can be used for filtering out payment methods that are only available on specific platforms. Possible values:<br><br>* iOS<br>* Android<br>* Web | getChannel(): ?string | setChannel(?string channel): void |
| `countryCode` | `?string` | Optional | The shopper country code.<br><br>Format: [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)<br>Example: NL or DE | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `order` | [`?EncryptedOrderData2`](../../doc/models/encrypted-order-data-2.md) | Optional | The order information required for partial payments. | getOrder(): ?EncryptedOrderData2 | setOrder(?EncryptedOrderData2 order): void |
| `shopperConversionId` | `?string` | Optional | A unique ID to [connect the shopper to a single checkout session](https://docs.adyen.com/online-payments/checkout-settings#checkout-shopper-conversion-id) that uses multiple API requests. You can use this to get insights into conversion rates.<br><br>**Constraints**: *Maximum Length*: `256` | getShopperConversionId(): ?string | setShopperConversionId(?string shopperConversionId): void |
| `shopperEmail` | `?string` | Optional | The shopper's email address. We recommend that you provide this data, as it is used in velocity fraud checks. > Required for Visa and JCB transactions that require 3D Secure 2 authentication if you did not include the `telephoneNumber`. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperIP` | `?string` | Optional | The shopper's IP address. We recommend that you provide this data, as it is used in a number of risk checks (for instance, number of payment attempts or location-based checks).<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication for all web and mobile integrations, if you did not include the `shopperEmail`. For native mobile integrations, the field is required to support cases where authentication is routed to the redirect flow. This field is also mandatory for some merchants depending on your business model. For more information, [contact Support](https://www.adyen.help/hc/en-us/requests/new). | getShopperIP(): ?string | setShopperIP(?string shopperIP): void |
| `shopperLocale` | `?string` | Optional | The language for the payment. The value combines the two-letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) language code with the [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes) country code. For example, **nl-NL**.<br><br>When using Drop-in/Components, the specified language appears if your front-end global configuration does not set the `locale`. | getShopperLocale(): ?string | setShopperLocale(?string shopperLocale): void |
| `shopperReference` | `?string` | Optional | Required for recurring payments.<br>Your reference to uniquely identify this shopper, for example user ID or account ID. The value is case-sensitive and must be at least three characters.<br><br>> Your reference must not include personally identifiable information (PII) such as name or email address. | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |
| `splitCardFundingSources` | `?bool` | Optional | Boolean value indicating whether the card payment method should be split into separate debit and credit options.<br><br>**Default**: `false` | getSplitCardFundingSources(): ?bool | setSplitCardFundingSources(?bool splitCardFundingSources): void |
| `store` | `?string` | Optional | Required for Adyen for Platforms integrations if you are a platform model. This is your [reference](https://docs.adyen.com/api-explorer/Management/3/post/merchants/(merchantId)/stores#request-reference) (on [balance platform](https://docs.adyen.com/platforms)) or the [storeReference](https://docs.adyen.com/api-explorer/Account/latest/post/updateAccountHolder#request-accountHolderDetails-storeDetails-storeReference) (in the [classic integration](https://docs.adyen.com/classic-platforms/processing-payments/route-payment-to-store/#route-a-payment-to-a-store)) for the ecommerce or point-of-sale store that is processing the payment.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `16` | getStore(): ?string | setStore(?string store): void |
| `storeFiltrationMode` | [`?string(StoreFiltrationMode2Enum)`](../../doc/models/store-filtration-mode-2-enum.md) | Optional | Specifies how payment methods should be filtered based on the `store` parameter:<br><br>- **exclusive**: Only payment methods belonging to the specified `store` are returned.<br>- **inclusive**: Payment methods from the `store` and those not associated with any other store are returned. | getStoreFiltrationMode(): ?string | setStoreFiltrationMode(?string storeFiltrationMode): void |
| `telephoneNumber` | `?string` | Optional | The shopper's telephone number.<br>The phone number must include a plus sign (+) and a country code (1-3 digits), followed by the number (4-15 digits). If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`. | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentMethodsRequestBuilder;
use AdyenLib\Models\Builders\Amount2Builder;
use AdyenLib\Models\Builders\BrowserInfoBuilder;

$paymentMethodsRequest = PaymentMethodsRequestBuilder::init(
    'merchantAccount4'
)
    ->additionalData(
        [
            'key0' => 'additionalData2'
        ]
    )
    ->allowedPaymentMethods(
        [
            'allowedPaymentMethods7'
        ]
    )
    ->amount(
        Amount2Builder::init(
            'currency2',
            110
        )->build()
    )
    ->blockedPaymentMethods(
        [
            'blockedPaymentMethods0'
        ]
    )
    ->browserInfo(
        BrowserInfoBuilder::init(
            'acceptHeader6',
            30,
            false,
            'language0',
            56,
            36,
            88,
            'userAgent4'
        )
            ->javaScriptEnabled(false)
            ->build()
    )
    ->splitCardFundingSources(false)
    ->build();
```

