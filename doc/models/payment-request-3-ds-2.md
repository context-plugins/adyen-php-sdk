
# Payment Request 3 Ds 2

## Structure

`PaymentRequest3ds2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountInfo` | [`?AccountInfo`](../../doc/models/account-info.md) | Optional | Shopper account information for 3D Secure 2.<br><br>> For 3D Secure 2 transactions, we recommend that you include this object to increase the chances of achieving a frictionless flow. | getAccountInfo(): ?AccountInfo | setAccountInfo(?AccountInfo accountInfo): void |
| `additionalAmount` | [`?Amount`](../../doc/models/amount.md) | Optional | If you want a [BIN or card verification](https://docs.adyen.com/payment-methods/cards/bin-data-and-card-verification) request to use a non-zero value, assign this value to `additionalAmount` (while the amount must be still set to 0 to trigger BIN or card verification).<br>Required to be in the same currency as the `amount`. | getAdditionalAmount(): ?Amount | setAdditionalAmount(?Amount additionalAmount): void |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular payment request.<br><br>The `additionalData` object consists of entries, each of which includes the key and value. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | The amount information for the transaction (in [minor units](https://docs.adyen.com/development-resources/currency-codes)). For [BIN or card verification](https://docs.adyen.com/payment-methods/cards/bin-data-and-card-verification) requests, set amount to 0 (zero). | getAmount(): Amount | setAmount(Amount amount): void |
| `applicationInfo` | [`?ApplicationInfo`](../../doc/models/application-info.md) | Optional | Information about your application. For more details, see [Building Adyen solutions](https://docs.adyen.com/development-resources/building-adyen-solutions). | getApplicationInfo(): ?ApplicationInfo | setApplicationInfo(?ApplicationInfo applicationInfo): void |
| `billingAddress` | [`?Address`](../../doc/models/address.md) | Optional | The address where to send the invoice.<br><br>> The `billingAddress` object is required in the following scenarios. Include all of the fields within this object.<br>> <br>> * For 3D Secure 2 transactions in all browser-based and mobile implementations.<br>> * For cross-border payouts to and from Canada. | getBillingAddress(): ?Address | setBillingAddress(?Address billingAddress): void |
| `browserInfo` | [`?BrowserInfo`](../../doc/models/browser-info.md) | Optional | The shopper's browser information.<br><br>> For 3D Secure, the full object is required for web integrations. For mobile app integrations, include the `userAgent` and `acceptHeader` fields to indicate  that your integration can support a redirect in case a payment is routed to 3D Secure 2 redirect. | getBrowserInfo(): ?BrowserInfo | setBrowserInfo(?BrowserInfo browserInfo): void |
| `captureDelayHours` | `?int` | Optional | The delay between the authorisation and scheduled auto-capture, specified in hours. | getCaptureDelayHours(): ?int | setCaptureDelayHours(?int captureDelayHours): void |
| `dateOfBirth` | `?DateTime` | Optional | The shopper's date of birth.<br><br>Format [ISO-8601](https://www.w3.org/TR/NOTE-datetime): YYYY-MM-DD | getDateOfBirth(): ?\DateTime | setDateOfBirth(?\DateTime dateOfBirth): void |
| `dccQuote` | [`?ForexQuote11`](../../doc/models/forex-quote-11.md) | Optional | The forex quote as returned in the response of the forex service. | getDccQuote(): ?ForexQuote11 | setDccQuote(?ForexQuote11 dccQuote): void |
| `deliveryAddress` | [`?Address`](../../doc/models/address.md) | Optional | The address where the purchased goods should be delivered. | getDeliveryAddress(): ?Address | setDeliveryAddress(?Address deliveryAddress): void |
| `deliveryDate` | `?DateTime` | Optional | The date and time the purchased goods should be delivered.<br><br>Format [ISO 8601](https://www.w3.org/TR/NOTE-datetime): YYYY-MM-DDThh:mm:ss.sssTZD<br><br>Example: 2017-07-17T13:42:40.428+01:00 | getDeliveryDate(): ?\DateTime | setDeliveryDate(?\DateTime deliveryDate): void |
| `deviceFingerprint` | `?string` | Optional | A string containing the shopper's device fingerprint. For more information, refer to [Device fingerprinting](https://docs.adyen.com/risk-management/device-fingerprinting).<br><br>**Constraints**: *Maximum Length*: `5000` | getDeviceFingerprint(): ?string | setDeviceFingerprint(?string deviceFingerprint): void |
| `fraudOffset` | `?int` | Optional | An integer value that is added to the normal fraud score. The value can be either positive or negative. | getFraudOffset(): ?int | setFraudOffset(?int fraudOffset): void |
| `installments` | [`?Installments`](../../doc/models/installments.md) | Optional | Contains installment settings. For more information, refer to [Installments](https://docs.adyen.com/payment-methods/cards/credit-card-installments). | getInstallments(): ?Installments | setInstallments(?Installments installments): void |
| `localizedShopperStatement` | `?array<string,string>` | Optional | The `localizedShopperStatement` field lets you use dynamic values for your shopper statement in a local character set. If this parameter is left empty, not provided, or not applicable (in case of cross-border transactions), then **shopperStatement** is used.<br><br>Currently, `localizedShopperStatement` is only supported for payments with Visa, Mastercard, JCB, Diners, and Discover.<br><br>**Supported characters**: Hiragana, Katakana, Kanji, and alphanumeric. | getLocalizedShopperStatement(): ?array | setLocalizedShopperStatement(?array localizedShopperStatement): void |
| `mcc` | `?string` | Optional | The [merchant category code](https://en.wikipedia.org/wiki/Merchant_category_code) (MCC) is a four-digit number, which relates to a particular market segment. This code reflects the predominant activity that is conducted by the merchant. | getMcc(): ?string | setMcc(?string mcc): void |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `merchantOrderReference` | `?string` | Optional | This reference allows linking multiple transactions to each other for reporting purposes (i.e. order auth-rate). The reference should be unique per billing cycle.<br>The same merchant order reference should never be reused after the first authorised attempt. If used, this field should be supplied for all incoming authorisations.<br><br>> We strongly recommend you send the `merchantOrderReference` value to benefit from linking payment requests when authorisation retries take place. In addition, we recommend you provide `retry.orderAttemptNumber`, `retry.chainAttemptNumber`, and `retry.skipRetry` values in `PaymentRequest.additionalData`. | getMerchantOrderReference(): ?string | setMerchantOrderReference(?string merchantOrderReference): void |
| `merchantRiskIndicator` | [`?MerchantRiskIndicator11`](../../doc/models/merchant-risk-indicator-11.md) | Optional | Additional risk fields for 3D Secure 2.<br><br>> For 3D Secure 2 transactions, we recommend that you include this object to increase the chances of achieving a frictionless flow. | getMerchantRiskIndicator(): ?MerchantRiskIndicator11 | setMerchantRiskIndicator(?MerchantRiskIndicator11 merchantRiskIndicator): void |
| `metadata` | `?array<string,string>` | Optional | Metadata consists of entries, each of which includes a key and a value.<br>Limits:<br><br>* Maximum 20 key-value pairs per request. When exceeding, the "177" error occurs: "Metadata size exceeds limit".<br>* Maximum 20 characters per key.<br>* Maximum 80 characters per value. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `orderReference` | `?string` | Optional | When you are doing multiple partial (gift card) payments, this is the `pspReference` of the first payment. We use this to link the multiple payments to each other. As your own reference for linking multiple payments, use the `merchantOrderReference`instead. | getOrderReference(): ?string | setOrderReference(?string orderReference): void |
| `recurring` | [`?Recurring`](../../doc/models/recurring.md) | Optional | The recurring settings for the payment. Use this property when you want to enable [recurring payments](https://docs.adyen.com/classic-integration/recurring-payments). | getRecurring(): ?Recurring | setRecurring(?Recurring recurring): void |
| `recurringProcessingModel` | [`?string(RecurringProcessingModelEnum)`](../../doc/models/recurring-processing-model-enum.md) | Optional | Defines a recurring payment type. Required when creating a token to store payment details or using stored payment details.<br>Allowed values:<br><br>* `Subscription` – A transaction for a fixed or variable amount, which follows a fixed schedule.<br>* `CardOnFile` – With a card-on-file (CoF) transaction, card details are stored to enable one-click or omnichannel journeys, or simply to streamline the checkout process. Any subscription not following a fixed schedule is also considered a card-on-file transaction.<br>* `UnscheduledCardOnFile` – An unscheduled card-on-file (UCoF) transaction is a transaction that occurs on a non-fixed schedule and/or have variable amounts. For example, automatic top-ups when a cardholder's balance drops below a certain amount. | getRecurringProcessingModel(): ?string | setRecurringProcessingModel(?string recurringProcessingModel): void |
| `reference` | `string` | Required | The reference to uniquely identify a payment. This reference is used in all communication with you about the payment status. We recommend using a unique value per payment; however, it is not a requirement.<br>If you need to provide multiple references for a transaction, separate them with hyphens ("-").<br>Maximum length: 80 characters. | getReference(): string | setReference(string reference): void |
| `selectedBrand` | `?string` | Optional | Some payment methods require defining a value for this field to specify how to process the transaction.<br><br>For the Bancontact payment method, it can be set to:<br><br>* `maestro` (default), to be processed like a Maestro card, or<br>* `bcmc`, to be processed like a Bancontact card. | getSelectedBrand(): ?string | setSelectedBrand(?string selectedBrand): void |
| `selectedRecurringDetailReference` | `?string` | Optional | The `recurringDetailReference` you want to use for this payment. The value `LATEST` can be used to select the most recently stored recurring detail. | getSelectedRecurringDetailReference(): ?string | setSelectedRecurringDetailReference(?string selectedRecurringDetailReference): void |
| `sessionId` | `?string` | Optional | A session ID used to identify a payment session. | getSessionId(): ?string | setSessionId(?string sessionId): void |
| `shopperEmail` | `?string` | Optional | The shopper's email address. We recommend that you provide this data, as it is used in velocity fraud checks. > Required for Visa and JCB transactions that require 3D Secure 2 authentication if you did not include the `telephoneNumber`. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperIP` | `?string` | Optional | The shopper's IP address. We recommend that you provide this data, as it is used in a number of risk checks (for instance, number of payment attempts or location-based checks).<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication for all web and mobile integrations, if you did not include the `shopperEmail`. For native mobile integrations, the field is required to support cases where authentication is routed to the redirect flow. This field is also mandatory for some merchants depending on your business model. For more information, [contact Support](https://www.adyen.help/hc/en-us/requests/new). | getShopperIP(): ?string | setShopperIP(?string shopperIP): void |
| `shopperInteraction` | [`?string(ShopperInteractionEnum)`](../../doc/models/shopper-interaction-enum.md) | Optional | Specifies the sales channel, through which the shopper gives their card details, and whether the shopper is a returning customer.<br>For the web service API, Adyen assumes Ecommerce shopper interaction by default.<br><br>This field has the following possible values:<br><br>* `Ecommerce` - Online transactions where the cardholder is present (online). For better authorisation rates, we recommend sending the card security code (CSC) along with the request.<br>* `ContAuth` - Card on file and/or subscription transactions, where the cardholder is known to the merchant (returning customer). If the shopper is present (online), you can supply also the CSC to improve authorisation (one-click payment).<br>* `Moto` - Mail-order and telephone-order transactions where the shopper is in contact with the merchant via email or telephone.<br>* `POS` - Point-of-sale transactions where the shopper is physically present to make a payment using a secure payment terminal. | getShopperInteraction(): ?string | setShopperInteraction(?string shopperInteraction): void |
| `shopperLocale` | `?string` | Optional | The language for the payment. The value combines the two-letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) language code with the [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes) country code. For example, **nl-NL**.<br><br>When using Drop-in/Components, the specified language appears if your front-end global configuration does not set the `locale`. | getShopperLocale(): ?string | setShopperLocale(?string shopperLocale): void |
| `shopperName` | [`?Name`](../../doc/models/name.md) | Optional | The shopper's full name. | getShopperName(): ?Name | setShopperName(?Name shopperName): void |
| `shopperReference` | `?string` | Optional | Required for recurring payments.<br>Your reference to uniquely identify this shopper, for example user ID or account ID. The value is case-sensitive and must be at least three characters.<br><br>> Your reference must not include personally identifiable information (PII) such as name or email address. | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |
| `shopperStatement` | `?string` | Optional | The text to be shown on the shopper's bank statement.<br>We recommend sending a maximum of 22 characters, otherwise banks might truncate the string.<br>Allowed characters: **a-z**, **A-Z**, **0-9**, spaces, and special characters **. , ' _ - ? + * /**. | getShopperStatement(): ?string | setShopperStatement(?string shopperStatement): void |
| `socialSecurityNumber` | `?string` | Optional | The shopper's social security number. | getSocialSecurityNumber(): ?string | setSocialSecurityNumber(?string socialSecurityNumber): void |
| `splits` | [`?(Split[])`](../../doc/models/split.md) | Optional | An array of objects specifying how the payment should be split when using either Adyen for Platforms for [marketplaces](https://docs.adyen.com/marketplaces/split-payments) or [platforms](https://docs.adyen.com/platforms/split-payments), or standalone [Issuing](https://docs.adyen.com/issuing/add-manage-funds#split). | getSplits(): ?array | setSplits(?array splits): void |
| `store` | `?string` | Optional | Required for Adyen for Platforms integrations if you are a platform model. This is your [reference](https://docs.adyen.com/api-explorer/Management/3/post/merchants/(merchantId)/stores#request-reference) (on [balance platform](https://docs.adyen.com/platforms)) or the [storeReference](https://docs.adyen.com/api-explorer/Account/latest/post/updateAccountHolder#request-accountHolderDetails-storeDetails-storeReference) (in the [classic integration](https://docs.adyen.com/classic-platforms/processing-payments/route-payment-to-store/#route-a-payment-to-a-store)) for the ecommerce or point-of-sale store that is processing the payment.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `16` | getStore(): ?string | setStore(?string store): void |
| `telephoneNumber` | `?string` | Optional | The shopper's telephone number.<br>The phone number must include a plus sign (+) and a country code (1-3 digits), followed by the number (4-15 digits). If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`. | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |
| `threeDS2RequestData` | [`?ThreeDS2RequestData11`](../../doc/models/three-ds-2-request-data-11.md) | Optional | Request fields for 3D Secure 2. To check if any of the following fields are required for your integration, refer to [Online payments](https://docs.adyen.com/online-payments) or [Classic integration](https://docs.adyen.com/classic-integration) documentation. | getThreeDS2RequestData(): ?ThreeDS2RequestData11 | setThreeDS2RequestData(?ThreeDS2RequestData11 threeDS2RequestData): void |
| `threeDS2Result` | [`?ThreeDS2Result`](../../doc/models/three-ds-2-result.md) | Optional | The ThreeDS2Result that was returned in the final CRes. | getThreeDS2Result(): ?ThreeDS2Result | setThreeDS2Result(?ThreeDS2Result threeDS2Result): void |
| `threeDS2Token` | `?string` | Optional | The ThreeDS2Token that was returned in the /authorise call. | getThreeDS2Token(): ?string | setThreeDS2Token(?string threeDS2Token): void |
| `threeDSAuthenticationOnly` | `?bool` | Optional | Required to trigger the [authentication-only flow](https://docs.adyen.com/online-payments/3d-secure/authentication-only/). If set to **true**, you will only perform the 3D Secure 2 authentication, and will not proceed to the payment authorization.Default: **false**.<br><br>**Default**: `false` | getThreeDSAuthenticationOnly(): ?bool | setThreeDSAuthenticationOnly(?bool threeDSAuthenticationOnly): void |
| `totalsGroup` | `?string` | Optional | The reference value to aggregate sales totals in reporting. When not specified, the store field is used (if available).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `16` | getTotalsGroup(): ?string | setTotalsGroup(?string totalsGroup): void |
| `trustedShopper` | `?bool` | Optional | Set to true if the payment should be routed to a trusted MID. | getTrustedShopper(): ?bool | setTrustedShopper(?bool trustedShopper): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentRequest3ds2Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\AccountInfoBuilder;
use AdyenLib\Models\AccountAgeIndicatorEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\AccountChangeIndicatorEnum;
use AdyenLib\Models\AccountTypeEnum;
use AdyenLib\Models\Builders\ApplicationInfoBuilder;
use AdyenLib\Models\Builders\CommonField4Builder;
use AdyenLib\Models\Builders\CommonField1Builder;
use AdyenLib\Models\Builders\ExternalPlatformBuilder;
use AdyenLib\Models\Builders\CommonField2Builder;
use AdyenLib\Models\Builders\MerchantDeviceBuilder;
use AdyenLib\Models\Builders\AddressBuilder;

$paymentRequest3ds2 = PaymentRequest3ds2Builder::init(
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount6',
    'reference0'
)
    ->accountInfo(
        AccountInfoBuilder::init()
            ->accountAgeIndicator(AccountAgeIndicatorEnum::FROM30TO60DAYS)
            ->accountChangeDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->accountChangeIndicator(AccountChangeIndicatorEnum::THISTRANSACTION)
            ->accountCreationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->accountType(AccountTypeEnum::NOTAPPLICABLE)
            ->build()
    )
    ->additionalAmount(
        AmountBuilder::init(
            'currency8',
            106
        )->build()
    )
    ->additionalData(
        [
            'key0' => 'additionalData4',
            'key1' => 'additionalData5',
            'key2' => 'additionalData6'
        ]
    )
    ->applicationInfo(
        ApplicationInfoBuilder::init()
            ->adyenLibrary(
                CommonField4Builder::init()
                    ->name('name8')
                    ->version('version4')
                    ->build()
            )
            ->adyenPaymentSource(
                CommonField1Builder::init()
                    ->name('name2')
                    ->version('version8')
                    ->build()
            )
            ->externalPlatform(
                ExternalPlatformBuilder::init()
                    ->integrator('integrator0')
                    ->name('name4')
                    ->version('version0')
                    ->build()
            )
            ->merchantApplication(
                CommonField2Builder::init()
                    ->name('name2')
                    ->version('version8')
                    ->build()
            )
            ->merchantDevice(
                MerchantDeviceBuilder::init()
                    ->os('os4')
                    ->osVersion('osVersion6')
                    ->reference('reference8')
                    ->build()
            )
            ->build()
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
    ->threeDSAuthenticationOnly(false)
    ->build();
```

