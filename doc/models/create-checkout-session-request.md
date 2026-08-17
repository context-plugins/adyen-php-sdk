
# Create Checkout Session Request

## Structure

`CreateCheckoutSessionRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountInfo` | [`?AccountInfo`](../../doc/models/account-info.md) | Optional | Shopper account information for 3D Secure 2.<br><br>> For 3D Secure 2 transactions, we recommend that you include this object to increase the chances of achieving a frictionless flow. | getAccountInfo(): ?AccountInfo | setAccountInfo(?AccountInfo accountInfo): void |
| `additionalAmount` | [`?Amount1`](../../doc/models/amount-1.md) | Optional | If you want a [BIN or card verification](https://docs.adyen.com/payment-methods/cards/bin-data-and-card-verification) request to use a non-zero value, assign this value to `additionalAmount` (while the amount must be still set to 0 to trigger BIN or card verification).<br>Required to be in the same currency as the `amount`. | getAdditionalAmount(): ?Amount1 | setAdditionalAmount(?Amount1 additionalAmount): void |
| `additionalData` | `?array<string,string>` | Optional | This field contains additional data, which may be required for a particular payment request.<br><br>The `additionalData` object consists of entries, each of which includes the key and value. | getAdditionalData(): ?array | setAdditionalData(?array additionalData): void |
| `allowedPaymentMethods` | `?(string[])` | Optional | List of payment methods to be presented to the shopper. To refer to payment methods, use their [payment method type](https://docs.adyen.com/payment-methods/payment-method-types).<br><br>Example: `"allowedPaymentMethods":["ideal","applepay"]` | getAllowedPaymentMethods(): ?array | setAllowedPaymentMethods(?array allowedPaymentMethods): void |
| `amount` | [`Amount18`](../../doc/models/amount-18.md) | Required | The amount of the payment. | getAmount(): Amount18 | setAmount(Amount18 amount): void |
| `applicationInfo` | [`?ApplicationInfo`](../../doc/models/application-info.md) | Optional | Information about your application. For more details, see [Building Adyen solutions](https://docs.adyen.com/development-resources/building-adyen-solutions). | getApplicationInfo(): ?ApplicationInfo | setApplicationInfo(?ApplicationInfo applicationInfo): void |
| `authenticationData` | [`?AuthenticationData1`](../../doc/models/authentication-data-1.md) | Optional | Configuration data for 3DS payments. | getAuthenticationData(): ?AuthenticationData1 | setAuthenticationData(?AuthenticationData1 authenticationData): void |
| `billingAddress` | [`?BillingAddress1`](../../doc/models/billing-address-1.md) | Optional | The address where to send the invoice. | getBillingAddress(): ?BillingAddress1 | setBillingAddress(?BillingAddress1 billingAddress): void |
| `blockedPaymentMethods` | `?(string[])` | Optional | List of payment methods to be hidden from the shopper. To refer to payment methods, use their [payment method type](https://docs.adyen.com/payment-methods/payment-method-types).<br><br>Example: `"blockedPaymentMethods":["ideal","applepay"]` | getBlockedPaymentMethods(): ?array | setBlockedPaymentMethods(?array blockedPaymentMethods): void |
| `captureDelayHours` | `?int` | Optional | The delay between the authorisation and scheduled auto-capture, specified in hours. | getCaptureDelayHours(): ?int | setCaptureDelayHours(?int captureDelayHours): void |
| `channel` | [`?string(ChannelEnum)`](../../doc/models/channel-enum.md) | Optional | The platform where a payment transaction takes place. This field is optional for filtering out payment methods that are only available on specific platforms. If this value is not set, then we will try to infer it from the `sdkVersion` or `token`.<br><br>Possible values:<br><br>* **iOS**<br>* **Android**<br>* **Web** | getChannel(): ?string | setChannel(?string channel): void |
| `company` | [`?Company1`](../../doc/models/company-1.md) | Optional | Information regarding the company. | getCompany(): ?Company1 | setCompany(?Company1 company): void |
| `countryCode` | `?string` | Optional | The shopper's two-letter country code. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `dateOfBirth` | `?DateTime` | Optional | The shopper's date of birth.<br><br>Format [ISO-8601](https://www.w3.org/TR/NOTE-datetime): YYYY-MM-DD | getDateOfBirth(): ?\DateTime | setDateOfBirth(?\DateTime dateOfBirth): void |
| `deliverAt` | `?DateTime` | Optional | The date and time when the purchased goods should be delivered.<br><br>[ISO 8601](https://www.w3.org/TR/NOTE-datetime) format: YYYY-MM-DDThh:mm:ss+TZD, for example, **2020-12-18T10:15:30+01:00**. | getDeliverAt(): ?\DateTime | setDeliverAt(?\DateTime deliverAt): void |
| `deliveryAddress` | [`?DeliveryAddress1`](../../doc/models/delivery-address-1.md) | Optional | The address where the purchased goods should be delivered. | getDeliveryAddress(): ?DeliveryAddress1 | setDeliveryAddress(?DeliveryAddress1 deliveryAddress): void |
| `enableOneClick` | `?bool` | Optional | When true and `shopperReference` is provided, the shopper will be asked if the payment details should be stored for future [one-click payments](https://docs.adyen.com/get-started-with-adyen/payment-glossary/#one-click-payments-definition). | getEnableOneClick(): ?bool | setEnableOneClick(?bool enableOneClick): void |
| `enablePayOut` | `?bool` | Optional | When true and `shopperReference` is provided, the payment details will be tokenized for payouts. | getEnablePayOut(): ?bool | setEnablePayOut(?bool enablePayOut): void |
| `enableRecurring` | `?bool` | Optional | When true and `shopperReference` is provided, the payment details will be stored for [recurring payments](https://docs.adyen.com/online-payments/tokenization/#recurring-payment-types) where the shopper is not present, such as subscription or automatic top-up payments. | getEnableRecurring(): ?bool | setEnableRecurring(?bool enableRecurring): void |
| `expiresAt` | `?DateTime` | Optional | The date the session expires in [ISO8601](https://www.iso.org/iso-8601-date-and-time-format.html) format. When not specified, the expiry date is set to 1 hour after session creation. You cannot set the session expiry to more than 24 hours after session creation. | getExpiresAt(): ?\DateTime | setExpiresAt(?\DateTime expiresAt): void |
| `fundOrigin` | [`?FundOrigin1`](../../doc/models/fund-origin-1.md) | Optional | The person or entity funding the money. | getFundOrigin(): ?FundOrigin1 | setFundOrigin(?FundOrigin1 fundOrigin): void |
| `fundRecipient` | [`?FundRecipient1`](../../doc/models/fund-recipient-1.md) | Optional | the person or entity receiving the money | getFundRecipient(): ?FundRecipient1 | setFundRecipient(?FundRecipient1 fundRecipient): void |
| `installmentOptions` | [`?array<string,CheckoutSessionInstallmentOption>`](../../doc/models/checkout-session-installment-option.md) | Optional | A set of key-value pairs that specifies the installment options available per payment method. The key must be a payment method name in lowercase. For example, **card** to specify installment options for all cards, or **visa** or **mc**. The value must be an object containing the installment options. | getInstallmentOptions(): ?array | setInstallmentOptions(?array installmentOptions): void |
| `lineItems` | [`?(LineItem[])`](../../doc/models/line-item.md) | Optional | Price and product information about the purchased items, to be included on the invoice sent to the shopper.<br><br>> This field is required for 3x 4x Oney, Affirm, Afterpay, Clearpay, Klarna, Ratepay, and Riverty. | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `mandate` | [`?Mandate`](../../doc/models/mandate.md) | Optional | The mandate details to initiate recurring transaction. | getMandate(): ?Mandate | setMandate(?Mandate mandate): void |
| `mcc` | `?string` | Optional | The [merchant category code](https://en.wikipedia.org/wiki/Merchant_category_code) (MCC) is a four-digit number, which relates to a particular market segment. This code reflects the predominant activity that is conducted by the merchant. | getMcc(): ?string | setMcc(?string mcc): void |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `merchantOrderReference` | `?string` | Optional | This reference allows linking multiple transactions to each other for reporting purposes (i.e. order auth-rate). The reference should be unique per billing cycle.<br>The same merchant order reference should never be reused after the first authorised attempt. If used, this field should be supplied for all incoming authorisations.<br><br>> We strongly recommend you send the `merchantOrderReference` value to benefit from linking payment requests when authorisation retries take place. In addition, we recommend you provide `retry.orderAttemptNumber`, `retry.chainAttemptNumber`, and `retry.skipRetry` values in `PaymentRequest.additionalData`. | getMerchantOrderReference(): ?string | setMerchantOrderReference(?string merchantOrderReference): void |
| `metadata` | `?array<string,string>` | Optional | Metadata consists of entries, each of which includes a key and a value.<br>Limits:<br><br>* Maximum 20 key-value pairs per request.<br>* Maximum 20 characters per key.<br>* Maximum 80 characters per value. | getMetadata(): ?array | setMetadata(?array metadata): void |
| `mode` | [`?string(ModeEnum)`](../../doc/models/mode-enum.md) | Optional | Indicates the type of front end integration. Possible values:<br><br>* **embedded** (default): Drop-in or Components integration<br>* **hosted**: Hosted Checkout integration<br><br>**Default**: `ModeEnum::EMBEDDED` | getMode(): ?string | setMode(?string mode): void |
| `mpiData` | [`?ThreeDSecureData`](../../doc/models/three-d-secure-data.md) | Optional | Authentication data produced by an MPI (Mastercard SecureCode, Visa Secure, or Cartes Bancaires). | getMpiData(): ?ThreeDSecureData | setMpiData(?ThreeDSecureData mpiData): void |
| `platformChargebackLogic` | [`?PlatformChargebackLogic`](../../doc/models/platform-chargeback-logic.md) | Optional | Defines how to book chargebacks when using [Adyen for Platforms](https://docs.adyen.com/adyen-for-platforms-model). | getPlatformChargebackLogic(): ?PlatformChargebackLogic | setPlatformChargebackLogic(?PlatformChargebackLogic platformChargebackLogic): void |
| `recurringExpiry` | `?string` | Optional | Date after which no further authorisations shall be performed. Only for 3D Secure 2. | getRecurringExpiry(): ?string | setRecurringExpiry(?string recurringExpiry): void |
| `recurringFrequency` | `?string` | Optional | Minimum number of days between authorisations. Only for 3D Secure 2. | getRecurringFrequency(): ?string | setRecurringFrequency(?string recurringFrequency): void |
| `recurringProcessingModel` | [`?string(RecurringProcessingModel1Enum)`](../../doc/models/recurring-processing-model-1-enum.md) | Optional | Defines a recurring payment type. Required when creating a token to store payment details.<br>Allowed values:<br><br>* `Subscription` – A transaction for a fixed or variable amount, which follows a fixed schedule.<br>* `CardOnFile` – With a card-on-file (CoF) transaction, card details are stored to enable one-click or omnichannel journeys, or simply to streamline the checkout process. Any subscription not following a fixed schedule is also considered a card-on-file transaction.<br>* `UnscheduledCardOnFile` – An unscheduled card-on-file (UCoF) transaction is a transaction that occurs on a non-fixed schedule and/or have variable amounts. For example, automatic top-ups when a cardholder's balance drops below a certain amount. | getRecurringProcessingModel(): ?string | setRecurringProcessingModel(?string recurringProcessingModel): void |
| `redirectFromIssuerMethod` | `?string` | Optional | Specifies the redirect method (GET or POST) when redirecting back from the issuer. | getRedirectFromIssuerMethod(): ?string | setRedirectFromIssuerMethod(?string redirectFromIssuerMethod): void |
| `redirectToIssuerMethod` | `?string` | Optional | Specifies the redirect method (GET or POST) when redirecting to the issuer. | getRedirectToIssuerMethod(): ?string | setRedirectToIssuerMethod(?string redirectToIssuerMethod): void |
| `reference` | `string` | Required | The reference to uniquely identify a payment. | getReference(): string | setReference(string reference): void |
| `returnUrl` | `string` | Required | The URL to return to in case of a redirection.<br>The format depends on the channel.<br><br>* For web, include the protocol `http://` or `https://`. You can also include your own additional query parameters, for example, shopper ID or order reference number.<br>  Example: `https://your-company.example.com/checkout?shopperOrder=12xy`<br>* For iOS, use the custom URL for your app. To know more about setting custom URL schemes, refer to the [Apple Developer documentation](https://developer.apple.com/documentation/uikit/inter-process_communication/allowing_apps_and_websites_to_link_to_your_content/defining_a_custom_url_scheme_for_your_app).<br>  Example: `my-app://`<br>* For Android, use a custom URL handled by an Activity on your app. You can configure it with an [intent filter](https://developer.android.com/guide/components/intents-filters).<br>  Example: `my-app://your.package.name`<br><br>If the URL to return to includes non-ASCII characters, like spaces or special letters, URL encode the value.<br><br>> The URL must not include personally identifiable information (PII), for example name or email address.<br><br>**Constraints**: *Maximum Length*: `1024` | getReturnUrl(): string | setReturnUrl(string returnUrl): void |
| `riskData` | [`?RiskData1`](../../doc/models/risk-data-1.md) | Optional | Any risk-related settings to apply to the payment. | getRiskData(): ?RiskData1 | setRiskData(?RiskData1 riskData): void |
| `shopperConversionId` | `?string` | Optional | Use this if you made a `/paymentMethods` request to get the payment methods for the shopper's checkout session.<br><br>A unique ID to [connect the shopper to a single checkout session](https://docs.adyen.com/online-payments/checkout-settings#checkout-shopper-conversion-id) that uses multiple API requests. You can use this to get insights into conversion rates.<br><br>**Constraints**: *Maximum Length*: `256` | getShopperConversionId(): ?string | setShopperConversionId(?string shopperConversionId): void |
| `shopperEmail` | `?string` | Optional | The shopper's email address. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperIP` | `?string` | Optional | The shopper's IP address. We recommend that you provide this data, as it is used in a number of risk checks (for instance, number of payment attempts or location-based checks).<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication for all web and mobile integrations, if you did not include the `shopperEmail`. For native mobile integrations, the field is required to support cases where authentication is routed to the redirect flow. This field is also mandatory for some merchants depending on your business model. For more information, [contact Support](https://www.adyen.help/hc/en-us/requests/new). | getShopperIP(): ?string | setShopperIP(?string shopperIP): void |
| `shopperInteraction` | [`?string(ShopperInteractionEnum)`](../../doc/models/shopper-interaction-enum.md) | Optional | Specifies the sales channel, through which the shopper gives their card details, and whether the shopper is a returning customer.<br>For the web service API, Adyen assumes Ecommerce shopper interaction by default.<br><br>This field has the following possible values:<br><br>* `Ecommerce` - Online transactions where the cardholder is present (online). For better authorisation rates, we recommend sending the card security code (CSC) along with the request.<br>* `ContAuth` - Card on file and/or subscription transactions, where the cardholder is known to the merchant (returning customer). If the shopper is present (online), you can supply also the CSC to improve authorisation (one-click payment).<br>* `Moto` - Mail-order and telephone-order transactions where the shopper is in contact with the merchant via email or telephone.<br>* `POS` - Point-of-sale transactions where the shopper is physically present to make a payment using a secure payment terminal. | getShopperInteraction(): ?string | setShopperInteraction(?string shopperInteraction): void |
| `shopperLocale` | `?string` | Optional | The language for the payment. The value combines the two-letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) language code with the [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes) country code. For example, **nl-NL**.<br><br>When using Drop-in/Components, the specified language appears if your front-end global configuration does not set the `locale`. | getShopperLocale(): ?string | setShopperLocale(?string shopperLocale): void |
| `shopperName` | [`?ShopperName1`](../../doc/models/shopper-name-1.md) | Optional | The shopper's full name. This object is required for some payment methods such as AfterPay, Klarna, or if you're enrolled in the PayPal Seller Protection program. | getShopperName(): ?ShopperName1 | setShopperName(?ShopperName1 shopperName): void |
| `shopperReference` | `?string` | Optional | Your reference to uniquely identify this shopper, for example user ID or account ID. The value is case-sensitive and must be at least three characters.<br><br>> Your reference must not include personally identifiable information (PII) such as name or email address.<br><br>**Constraints**: *Minimum Length*: `3`, *Maximum Length*: `256` | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |
| `shopperStatement` | `?string` | Optional | The text to be shown on the shopper's bank statement.<br>We recommend sending a maximum of 22 characters, otherwise banks might truncate the string.<br>Allowed characters: **a-z**, **A-Z**, **0-9**, spaces, and special characters **. , ' _ - ? + * /**. | getShopperStatement(): ?string | setShopperStatement(?string shopperStatement): void |
| `showInstallmentAmount` | `?bool` | Optional | Set to true to show the payment amount per installment. | getShowInstallmentAmount(): ?bool | setShowInstallmentAmount(?bool showInstallmentAmount): void |
| `showRemovePaymentMethodButton` | `?bool` | Optional | Set to **true** to show a button that lets the shopper remove a stored payment method. | getShowRemovePaymentMethodButton(): ?bool | setShowRemovePaymentMethodButton(?bool showRemovePaymentMethodButton): void |
| `socialSecurityNumber` | `?string` | Optional | The shopper's social security number. | getSocialSecurityNumber(): ?string | setSocialSecurityNumber(?string socialSecurityNumber): void |
| `splitCardFundingSources` | `?bool` | Optional | Boolean value indicating whether the card payment method should be split into separate debit and credit options.<br><br>**Default**: `false` | getSplitCardFundingSources(): ?bool | setSplitCardFundingSources(?bool splitCardFundingSources): void |
| `splits` | [`?(Split[])`](../../doc/models/split.md) | Optional | An array of objects specifying how to split a payment when using [Adyen for Platforms](https://docs.adyen.com/platforms/process-payments#providing-split-information), [Classic Platforms integration](https://docs.adyen.com/classic-platforms/processing-payments#providing-split-information), or [Issuing](https://docs.adyen.com/issuing/manage-funds#split). | getSplits(): ?array | setSplits(?array splits): void |
| `store` | `?string` | Optional | Required for Adyen for Platforms integrations if you are a platform model. This is your [reference](https://docs.adyen.com/api-explorer/Management/3/post/merchants/(merchantId)/stores#request-reference) (on [balance platform](https://docs.adyen.com/platforms)) or the [storeReference](https://docs.adyen.com/api-explorer/Account/latest/post/updateAccountHolder#request-accountHolderDetails-storeDetails-storeReference) (in the [classic integration](https://docs.adyen.com/classic-platforms/processing-payments/route-payment-to-store/#route-a-payment-to-a-store)) for the ecommerce or point-of-sale store that is processing the payment. | getStore(): ?string | setStore(?string store): void |
| `storeFiltrationMode` | [`?string(StoreFiltrationModeEnum)`](../../doc/models/store-filtration-mode-enum.md) | Optional | Specifies how payment methods should be filtered based on the 'store' parameter:<br><br>- 'exclusive': Only payment methods belonging to the specified 'store' are returned.<br>- 'inclusive': Payment methods from the 'store' and those not associated with any other store are returned. | getStoreFiltrationMode(): ?string | setStoreFiltrationMode(?string storeFiltrationMode): void |
| `storePaymentMethod` | `?bool` | Optional | When true and `shopperReference` is provided, the payment details will be stored for future [recurring payments](https://docs.adyen.com/online-payments/tokenization/#recurring-payment-types). | getStorePaymentMethod(): ?bool | setStorePaymentMethod(?bool storePaymentMethod): void |
| `storePaymentMethodMode` | [`?string(StorePaymentMethodModeEnum)`](../../doc/models/store-payment-method-mode-enum.md) | Optional | Indicates if the details of the payment method will be stored for the shopper. Possible values:<br><br>* **disabled** – No details will be stored (default).<br>* **askForConsent** – If the `shopperReference` is provided, the Drop-in/Component shows a checkbox where the shopper can select to store their payment details for card payments.<br>* **enabled** – If the `shopperReference` is provided, the details will be stored without asking the shopper for consent. | getStorePaymentMethodMode(): ?string | setStorePaymentMethodMode(?string storePaymentMethodMode): void |
| `telephoneNumber` | `?string` | Optional | The shopper's telephone number.<br>The phone number must include a plus sign (+) and a country code (1-3 digits), followed by the number (4-15 digits). If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`. | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |
| `themeId` | `?string` | Optional | Sets a custom theme for [Hosted Checkout](https://docs.adyen.com/online-payments/build-your-integration/?platform=Web&integration=Hosted+Checkout). The value can be any of the **Theme ID** values from your Customer Area. | getThemeId(): ?string | setThemeId(?string themeId): void |
| `thirdPartyTokenRedundancyInfo` | [`?ThirdPartyTokenRedundancyInfo1`](../../doc/models/third-party-token-redundancy-info-1.md) | Optional | Configuration for creating redundant payment tokens with third-party token vaults using the Adyen Forward API. This feature requires Forward API webhook integration and pre-configured templates in your Adyen account. Contact your Adyen account manager for setup and availability. | getThirdPartyTokenRedundancyInfo(): ?ThirdPartyTokenRedundancyInfo1 | setThirdPartyTokenRedundancyInfo(?ThirdPartyTokenRedundancyInfo1 thirdPartyTokenRedundancyInfo): void |
| `threeDS2RequestData` | [`?CheckoutSessionThreeDS2RequestData1`](../../doc/models/checkout-session-three-ds-2-request-data-1.md) | Optional | Request fields for 3D Secure 2. To check if any of the following fields are required for your integration, refer to [Online payments](https://docs.adyen.com/online-payments). | getThreeDS2RequestData(): ?CheckoutSessionThreeDS2RequestData1 | setThreeDS2RequestData(?CheckoutSessionThreeDS2RequestData1 threeDS2RequestData): void |
| `threeDSAuthenticationOnly` | `?bool` | Optional | Required to trigger the [authentication-only flow](https://docs.adyen.com/online-payments/3d-secure/authentication-only/). If set to **true**, you will only perform the 3D Secure 2 authentication, and will not proceed to the payment authorization.Default: **false**.<br><br>**Default**: `false` | getThreeDSAuthenticationOnly(): ?bool | setThreeDSAuthenticationOnly(?bool threeDSAuthenticationOnly): void |
| `trustedShopper` | `?bool` | Optional | Set to true if the payment should be routed to a trusted MID. | getTrustedShopper(): ?bool | setTrustedShopper(?bool trustedShopper): void |

## Example

```php
use AdyenLib\Models\Builders\CreateCheckoutSessionRequestBuilder;
use AdyenLib\Models\Builders\Amount18Builder;
use AdyenLib\Models\Builders\AccountInfoBuilder;
use AdyenLib\Models\AccountAgeIndicatorEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\AccountChangeIndicatorEnum;
use AdyenLib\Models\AccountTypeEnum;
use AdyenLib\Models\Builders\Amount1Builder;
use AdyenLib\Models\Builders\ApplicationInfoBuilder;
use AdyenLib\Models\Builders\CommonField4Builder;
use AdyenLib\Models\Builders\CommonField1Builder;
use AdyenLib\Models\Builders\ExternalPlatformBuilder;
use AdyenLib\Models\Builders\CommonField2Builder;
use AdyenLib\Models\Builders\MerchantDeviceBuilder;
use AdyenLib\Models\ModeEnum;

$createCheckoutSessionRequest = CreateCheckoutSessionRequestBuilder::init(
    Amount18Builder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount4',
    'reference0',
    'returnUrl8'
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
        Amount1Builder::init(
            'currency8',
            106
        )->build()
    )
    ->additionalData(
        [
            'key0' => 'additionalData4',
            'key1' => 'additionalData3'
        ]
    )
    ->allowedPaymentMethods(
        [
            'allowedPaymentMethods9',
            'allowedPaymentMethods0',
            'allowedPaymentMethods1'
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
    ->mode(ModeEnum::EMBEDDED)
    ->splitCardFundingSources(false)
    ->threeDSAuthenticationOnly(false)
    ->build();
```

