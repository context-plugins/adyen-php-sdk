
# Stored Value Load Request

## Structure

`StoredValueLoadRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount`](../../doc/models/amount.md) | Required | The amount information for the transaction. | getAmount(): Amount | setAmount(Amount amount): void |
| `loadType` | [`?string(LoadTypeEnum)`](../../doc/models/load-type-enum.md) | Optional | The type of load you are trying to do, when absent we default to 'load' | getLoadType(): ?string | setLoadType(?string loadType): void |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `paymentMethod` | `array<string,string>` | Required | The collection that contains the type of the payment method and its specific information if available | getPaymentMethod(): array | setPaymentMethod(array paymentMethod): void |
| `recurringDetailReference` | `?string` | Optional | - | getRecurringDetailReference(): ?string | setRecurringDetailReference(?string recurringDetailReference): void |
| `reference` | `string` | Required | The reference to uniquely identify a payment. This reference is used in all communication with you about the payment status. We recommend using a unique value per payment; however, it is not a requirement.<br>If you need to provide multiple references for a transaction, separate them with hyphens ("-").<br>Maximum length: 80 characters. | getReference(): string | setReference(string reference): void |
| `shopperInteraction` | [`?string(ShopperInteractionEnum)`](../../doc/models/shopper-interaction-enum.md) | Optional | Specifies the sales channel, through which the shopper gives their card details, and whether the shopper is a returning customer.<br>For the web service API, Adyen assumes Ecommerce shopper interaction by default.<br><br>This field has the following possible values:<br><br>* `Ecommerce` - Online transactions where the cardholder is present (online). For better authorisation rates, we recommend sending the card security code (CSC) along with the request.<br>* `ContAuth` - Card on file and/or subscription transactions, where the cardholder is known to the merchant (returning customer). If the shopper is present (online), you can supply also the CSC to improve authorisation (one-click payment).<br>* `Moto` - Mail-order and telephone-order transactions where the shopper is in contact with the merchant via email or telephone.<br>* `POS` - Point-of-sale transactions where the shopper is physically present to make a payment using a secure payment terminal. | getShopperInteraction(): ?string | setShopperInteraction(?string shopperInteraction): void |
| `shopperReference` | `?string` | Optional | - | getShopperReference(): ?string | setShopperReference(?string shopperReference): void |
| `store` | `?string` | Optional | The physical store, for which this payment is processed.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `16` | getStore(): ?string | setStore(?string store): void |

## Example

```php
use AdyenLib\Models\Builders\StoredValueLoadRequestBuilder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\LoadTypeEnum;
use AdyenLib\Models\ShopperInteractionEnum;

$storedValueLoadRequest = StoredValueLoadRequestBuilder::init(
    AmountBuilder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount8',
    [
        'key0' => 'paymentMethod8',
        'key1' => 'paymentMethod9'
    ],
    'reference2'
)
    ->loadType(LoadTypeEnum::MERCHANDISERETURN)
    ->recurringDetailReference('recurringDetailReference6')
    ->shopperInteraction(ShopperInteractionEnum::MOTO)
    ->shopperReference('shopperReference4')
    ->store('store6')
    ->build();
```

