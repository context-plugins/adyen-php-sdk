
# Payout Request

## Structure

`PayoutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | The amount information for the transaction (in [minor units](https://docs.adyen.com/development-resources/currency-codes)). For [BIN or card verification](https://docs.adyen.com/payment-methods/cards/bin-data-and-card-verification) requests, set amount to 0 (zero). | getAmount(): Amount | setAmount(Amount amount): void |
| `billingAddress` | [`?Address`](../../doc/models/address.md) | Optional | The address where to send the invoice.<br><br>> The `billingAddress` object is required in the following scenarios. Include all of the fields within this object.<br>> <br>> * For 3D Secure 2 transactions in all browser-based and mobile implementations.<br>> * For cross-border payouts to and from Canada. | getBillingAddress(): ?Address | setBillingAddress(?Address billingAddress): void |
| `card` | [`?Card`](../../doc/models/card.md) | Optional | A container for card data.<br><br>> Either `bankAccount` or `card` field must be provided in a payment request. | getCard(): ?Card | setCard(?Card card): void |
| `fraudOffset` | `?int` | Optional | An integer value that is added to the normal fraud score. The value can be either positive or negative. | getFraudOffset(): ?int | setFraudOffset(?int fraudOffset): void |
| `fundSource` | [`?FundSource11`](../../doc/models/fund-source-11.md) | Optional | The person or entity funding the money. | getFundSource(): ?FundSource11 | setFundSource(?FundSource11 fundSource): void |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `recurring` | [`?Recurring`](../../doc/models/recurring.md) | Optional | The recurring settings for the payment. Use this property when you want to enable [recurring payments](https://docs.adyen.com/classic-integration/recurring-payments). | getRecurring(): ?Recurring | setRecurring(?Recurring recurring): void |
| `reference` | `string` | Required | The reference to uniquely identify a payment. This reference is used in all communication with you about the payment status. We recommend using a unique value per payment; however, it is not a requirement.<br>If you need to provide multiple references for a transaction, separate them with hyphens ("-").<br>Maximum length: 80 characters. | getReference(): string | setReference(string reference): void |
| `selectedRecurringDetailReference` | `?string` | Optional | The `recurringDetailReference` you want to use for this payment. The value `LATEST` can be used to select the most recently stored recurring detail. | getSelectedRecurringDetailReference(): ?string | setSelectedRecurringDetailReference(?string selectedRecurringDetailReference): void |
| `shopperEmail` | `?string` | Optional | The shopper's email address. We recommend that you provide this data, as it is used in velocity fraud checks. > Required for Visa and JCB transactions that require 3D Secure 2 authentication if you did not include the `telephoneNumber`. | getShopperEmail(): ?string | setShopperEmail(?string shopperEmail): void |
| `shopperInteraction` | [`?string(ShopperInteractionEnum)`](../../doc/models/shopper-interaction-enum.md) | Optional | Specifies the sales channel, through which the shopper gives their card details, and whether the shopper is a returning customer.<br>For the web service API, Adyen assumes Ecommerce shopper interaction by default.<br><br>This field has the following possible values:<br><br>* `Ecommerce` - Online transactions where the cardholder is present (online). For better authorisation rates, we recommend sending the card security code (CSC) along with the request.<br>* `ContAuth` - Card on file and/or subscription transactions, where the cardholder is known to the merchant (returning customer). If the shopper is present (online), you can supply also the CSC to improve authorisation (one-click payment).<br>* `Moto` - Mail-order and telephone-order transactions where the shopper is in contact with the merchant via email or telephone.<br>* `POS` - Point-of-sale transactions where the shopper is physically present to make a payment using a secure payment terminal. | getShopperInteraction(): ?string | setShopperInteraction(?string shopperInteraction): void |
| `shopperName` | [`?Name`](../../doc/models/name.md) | Optional | The shopper's full name. | getShopperName(): ?Name | setShopperName(?Name shopperName): void |
| `shopperReference` | `?string` | Optional | Required for recurring payments.<br>Your reference to uniquely identify this shopper, for example user ID or account ID. The value is case-sensitive and must be at least three characters.<br><br>> Your reference must not include personally identifiable information (PII) such as name or email address. | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |
| `telephoneNumber` | `?string` | Optional | The shopper's telephone number.<br>The phone number must include a plus sign (+) and a country code (1-3 digits), followed by the number (4-15 digits). If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`. | getTelephoneNumber(): ?string | setTelephoneNumber(?string telephoneNumber): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\AddressBuilder;
use AdyenLib\Models\Builders\CardBuilder;
use AdyenLib\Models\Builders\FundSource11Builder;
use AdyenLib\Models\Builders\NameBuilder;
use AdyenLib\Models\Builders\RecurringBuilder;
use AdyenLib\Models\ContractEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\TokenServiceEnum;

$payoutRequest = PayoutRequestBuilder::init(
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount8',
    'reference8'
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
    ->fraudOffset(166)
    ->fundSource(
        FundSource11Builder::init()
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
                CardBuilder::init()
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
            )->build()
    )
    ->recurring(
        RecurringBuilder::init()
            ->contract(ContractEnum::ENUM_ONECLICKRECURRING)
            ->recurringDetailName('recurringDetailName2')
            ->recurringExpiry(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->recurringFrequency('recurringFrequency0')
            ->tokenService(TokenServiceEnum::VISATOKENSERVICE)
            ->build()
    )
    ->build();
```

