
# Cost Estimate Request

## Structure

`CostEstimateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | The transaction amount used as a base for the cost estimation. | getAmount(): Amount | setAmount(Amount amount): void |
| `assumptions` | [`?CostEstimateAssumptions1`](../../doc/models/cost-estimate-assumptions-1.md) | Optional | Assumptions made for the expected characteristics of the transaction, for which the charges are being estimated. | getAssumptions(): ?CostEstimateAssumptions1 | setAssumptions(?CostEstimateAssumptions1 assumptions): void |
| `cardNumber` | `?string` | Optional | The card number (4-19 characters) for PCI compliant use cases. Do not use any separators.<br><br>> Either the `cardNumber` or `encryptedCardNumber` field must be provided in a payment request.<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `19` | getCardNumber(): ?string | setCardNumber(?string cardNumber): void |
| `encryptedCardNumber` | `?string` | Optional | Encrypted data that stores card information for non PCI-compliant use cases. The encrypted data must be created with the Checkout Card Component or Secured Fields Component, and must contain the `encryptedCardNumber` field.<br><br>> Either the `cardNumber` or `encryptedCardNumber` field must be provided in a payment request. | getEncryptedCardNumber(): ?string | setEncryptedCardNumber(?string encryptedCardNumber): void |
| `merchantAccount` | `string` | Required | The merchant account identifier you want to process the (transaction) request with. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `merchantDetails` | [`?MerchantDetails2`](../../doc/models/merchant-details-2.md) | Optional | Additional data for merchants who don't use Adyen as the payment authorisation gateway. | getMerchantDetails(): ?MerchantDetails2 | setMerchantDetails(?MerchantDetails2 merchantDetails): void |
| `recurring` | [`?Recurring`](../../doc/models/recurring.md) | Optional | The recurring settings for the payment. Use this property when you want to enable [recurring payments](https://docs.adyen.com/online-payments/tokenization). | getRecurring(): ?Recurring | setRecurring(?Recurring recurring): void |
| `selectedRecurringDetailReference` | `?string` | Optional | The `recurringDetailReference` you want to use for this cost estimate. The value `LATEST` can be used to select the most recently stored recurring detail. | getSelectedRecurringDetailReference(): ?string | setSelectedRecurringDetailReference(?string selectedRecurringDetailReference): void |
| `shopperInteraction` | [`?string(ShopperInteractionEnum)`](../../doc/models/shopper-interaction-enum.md) | Optional | Specifies the sales channel, through which the shopper gives their card details, and whether the shopper is a returning customer.<br>For the web service API, Adyen assumes Ecommerce shopper interaction by default.<br><br>This field has the following possible values:<br><br>* `Ecommerce` - Online transactions where the cardholder is present (online). For better authorisation rates, we recommend sending the card security code (CSC) along with the request.<br>* `ContAuth` - Card on file and/or subscription transactions, where the card holder is known to the merchant (returning customer). If the shopper is present (online), you can supply also the CSC to improve authorisation (one-click payment).<br>* `Moto` - Mail-order and telephone-order transactions where the shopper is in contact with the merchant via email or telephone.<br>* `POS` - Point-of-sale transactions where the shopper is physically present to make a payment using a secure payment terminal. | getShopperInteraction(): ?string | setShopperInteraction(?string shopperInteraction): void |
| `shopperReference` | `?string` | Optional | Required for recurring payments.<br>Your reference to uniquely identify this shopper, for example user ID or account ID. The value is case-sensitive and must be at least three characters.<br><br>> Your reference must not include personally identifiable information (PII) such as name or email address. | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |

## Example

```php
use AdyenLib\Models\Builders\CostEstimateRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\CostEstimateAssumptions1Builder;
use AdyenLib\Models\Builders\MerchantDetails2Builder;
use AdyenLib\Models\Builders\RecurringBuilder;
use AdyenLib\Models\ContractEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\TokenServiceEnum;

$costEstimateRequest = CostEstimateRequestBuilder::init(
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount0'
)
    ->assumptions(
        CostEstimateAssumptions1Builder::init()
            ->assume3DSecureAuthenticated(false)
            ->assumeLevel3Data(false)
            ->installments(20)
            ->build()
    )
    ->cardNumber('cardNumber4')
    ->encryptedCardNumber('encryptedCardNumber4')
    ->merchantDetails(
        MerchantDetails2Builder::init()
            ->countryCode('countryCode8')
            ->enrolledIn3DSecure(false)
            ->mcc('mcc6')
            ->build()
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

