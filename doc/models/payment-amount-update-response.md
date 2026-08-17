
# Payment Amount Update Response

## Structure

`PaymentAmountUpdateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adjustAuthorisationData` | `?string` | Optional | The data blob for subsequent synchronous adjust authorisation calls. Returned when the synchronous flow is used. | getAdjustAuthorisationData(): ?string | setAdjustAuthorisationData(?string adjustAuthorisationData): void |
| `amount` | [`Amount30`](../../doc/models/amount-30.md) | Required | The updated amount. | getAmount(): Amount30 | setAmount(Amount30 amount): void |
| `industryUsage` | [`?string(IndustryUsage1Enum)`](../../doc/models/industry-usage-1-enum.md) | Optional | The reason for the amount update. Possible values:<br><br>* **delayedCharge**<br>* **noShow**<br>* **installment** | getIndustryUsage(): ?string | setIndustryUsage(?string industryUsage): void |
| `lineItems` | [`?(LineItem[])`](../../doc/models/line-item.md) | Optional | Price and product information of the refunded items, required for [partial refunds](https://docs.adyen.com/online-payments/refund#refund-a-payment).<br><br>> This field is required for partial refunds with 3x 4x Oney, Affirm, Afterpay, Atome, Clearpay, Klarna, Ratepay, Walley, and Zip. | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `merchantAccount` | `string` | Required | The merchant account that is used to process the payment. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `paymentPspReference` | `string` | Required | The [`pspReference`](https://docs.adyen.com/api-explorer/Checkout/latest/post/payments#responses-200-pspReference) of the payment to update. | getPaymentPspReference(): string | setPaymentPspReference(string paymentPspReference): void |
| `pspReference` | `string` | Required | Adyen's 16-character reference associated with the amount update request. | getPspReference(): string | setPspReference(string pspReference): void |
| `reference` | `string` | Required | Your reference for the amount update request. Maximum length: 80 characters. | getReference(): string | setReference(string reference): void |
| `splits` | [`?(Split[])`](../../doc/models/split.md) | Optional | An array of objects specifying how the amount should be split between accounts when using Adyen for Platforms. For more information, see how to process payments for [marketplaces](https://docs.adyen.com/marketplaces/process-payments) or [platforms](https://docs.adyen.com/platforms/process-payments). | getSplits(): ?array | setSplits(?array splits): void |
| `status` | [`string(Status2Enum)`](../../doc/models/status-2-enum.md) | Required | The status of your request.<br><br>If you included `adjustAuthorisationData` in your request, possible values are the following:<br><br>* **authorised**<br><br>* **refused**<br><br>Otherwise, the value is **received**. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentAmountUpdateResponseBuilder;
use AdyenLib\Models\Builders\Amount30Builder;
use AdyenLib\Models\Status2Enum;
use AdyenLib\Models\IndustryUsage1Enum;
use AdyenLib\Models\Builders\LineItemBuilder;
use AdyenLib\Models\Builders\SplitBuilder;
use AdyenLib\Models\Type11Enum;
use AdyenLib\Models\Builders\SplitAmountBuilder;

$paymentAmountUpdateResponse = PaymentAmountUpdateResponseBuilder::init(
    Amount30Builder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount2',
    'paymentPspReference8',
    'pspReference2',
    'reference6',
    Status2Enum::REFUSED
)
    ->adjustAuthorisationData('adjustAuthorisationData8')
    ->industryUsage(IndustryUsage1Enum::DELAYEDCHARGE)
    ->lineItems(
        [
            LineItemBuilder::init()
                ->amountExcludingTax(38)
                ->amountIncludingTax(148)
                ->brand('brand6')
                ->color('color6')
                ->description('description2')
                ->build()
        ]
    )
    ->splits(
        [
            SplitBuilder::init(
                Type11Enum::DEFAULT_
            )
                ->account('account2')
                ->amount(
                    SplitAmountBuilder::init(
                        110
                    )
                        ->currency('currency2')
                        ->build()
                )
                ->description('description2')
                ->reference('reference2')
                ->build()
        ]
    )
    ->build();
```

