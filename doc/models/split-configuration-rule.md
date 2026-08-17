
# Split Configuration Rule

## Structure

`SplitConfigurationRule`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardRegion` | [`?string(CardRegionEnum)`](../../doc/models/card-region-enum.md) | Optional | The card region condition that determines whether the [split logic](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/(merchantId)/splitConfigurations#request-rules-splitLogic) applies to the transaction.<br><br>> This condition is in pilot phase, and not yet available for all platforms.<br><br>Possible values:<br><br>* **domestic**: The card issuer and the store where the transaction is processed are registered in the same country.<br>* **international**: The card issuer and the store where the transaction is processed are registered in different countries or regions. Includes all **interRegional** and **intraRegional** transactions.<br>* **interRegional**: The card issuer and the store where the transaction is processed are registered in different regions.<br>* **intraRegional**: The card issuer and the store where the transaction is processed are registered in different countries, but in the same region.<br>* **intraEEA**: The card issuer and the store where the transaction is processed are registered in different countries, but in the European Economic Area (EEA).<br>* **ANY**: Applies to all transactions, regardless of the processing and issuing country/region. | getCardRegion(): ?string | setCardRegion(?string cardRegion): void |
| `currency` | `string` | Required | The currency condition that defines whether the split logic applies.<br>Its value must be a three-character [ISO currency code](https://en.wikipedia.org/wiki/ISO_4217). | getCurrency(): string | setCurrency(string currency): void |
| `fundingSource` | [`string(FundingSource1Enum)`](../../doc/models/funding-source-1-enum.md) | Required | The funding source of the payment method.<br><br>Possible values:<br><br>* **credit**<br>* **debit**<br>* **prepaid**<br>* **deferred_debit**<br>* **charged**<br>* **ANY** | getFundingSource(): string | setFundingSource(string fundingSource): void |
| `paymentMethod` | `string` | Required | The payment method condition that defines whether the split logic applies.<br><br>Possible values:<br><br>* [Payment method variant](https://docs.adyen.com/development-resources/paymentmethodvariant): Apply the split logic for a specific payment method.<br>* **ANY**: Apply the split logic for all available payment methods. | getPaymentMethod(): string | setPaymentMethod(string paymentMethod): void |
| `ruleId` | `?string` | Optional, Read-only | The unique identifier of the split configuration rule. | getRuleId(): ?string | setRuleId(?string ruleId): void |
| `shopperInteraction` | [`string(ShopperInteraction11Enum)`](../../doc/models/shopper-interaction-11-enum.md) | Required | The sales channel condition that defines whether the split logic applies.<br><br>Possible values:<br><br>* **Ecommerce**: Online transactions where the cardholder is present.<br>* **ContAuth**: Card on file and/or subscription transactions, where the cardholder is known to the merchant (returning customer).<br>* **Moto**: Mail-order and telephone-order transactions where the customer is in contact with the merchant via email or telephone.<br>* **POS**: Point-of-sale transactions where the customer is physically present to make a payment using a secure payment terminal.<br>* **ANY**: All sales channels. | getShopperInteraction(): string | setShopperInteraction(string shopperInteraction): void |
| `splitLogic` | [`SplitConfigurationLogic2`](../../doc/models/split-configuration-logic-2.md) | Required | Contains the split logic that is applied if the rule conditions are met. | getSplitLogic(): SplitConfigurationLogic2 | setSplitLogic(SplitConfigurationLogic2 splitLogic): void |

## Example

```php
use AdyenLib\Models\Builders\SplitConfigurationRuleBuilder;
use AdyenLib\Models\FundingSource1Enum;
use AdyenLib\Models\ShopperInteraction11Enum;
use AdyenLib\Models\Builders\SplitConfigurationLogic2Builder;
use AdyenLib\Models\Builders\Commission1Builder;
use AdyenLib\Models\AcquiringFeesEnum;
use AdyenLib\Models\Builders\AdditionalCommission1Builder;
use AdyenLib\Models\AdyenCommissionEnum;
use AdyenLib\Models\AdyenFeesEnum;
use AdyenLib\Models\AdyenMarkupEnum;
use AdyenLib\Models\CardRegionEnum;

$splitConfigurationRule = SplitConfigurationRuleBuilder::init(
    'currency6',
    FundingSource1Enum::PREPAID,
    'paymentMethod6',
    ShopperInteraction11Enum::MOTO,
    SplitConfigurationLogic2Builder::init(
        Commission1Builder::init()
            ->fixedAmount(112)
            ->variablePercentage(52)
            ->build()
    )
        ->acquiringFees(AcquiringFeesEnum::DEDUCTFROMLIABLEACCOUNT)
        ->additionalCommission(
            AdditionalCommission1Builder::init()
                ->balanceAccountId('balanceAccountId0')
                ->fixedAmount(100)
                ->variablePercentage(64)
                ->build()
        )
        ->adyenCommission(AdyenCommissionEnum::DEDUCTFROMLIABLEACCOUNT)
        ->adyenFees(AdyenFeesEnum::DEDUCTFROMLIABLEACCOUNT)
        ->adyenMarkup(AdyenMarkupEnum::DEDUCTFROMLIABLEACCOUNT)
        ->build()
)
    ->cardRegion(CardRegionEnum::INTERNATIONAL)
    ->build();
```

