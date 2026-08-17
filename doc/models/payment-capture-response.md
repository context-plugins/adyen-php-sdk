
# Payment Capture Response

## Structure

`PaymentCaptureResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount33`](../../doc/models/amount-33.md) | Required | The captured amount. | getAmount(): Amount33 | setAmount(Amount33 amount): void |
| `lineItems` | [`?(LineItem[])`](../../doc/models/line-item.md) | Optional | Price and product information of the refunded items, required for [partial refunds](https://docs.adyen.com/online-payments/refund#refund-a-payment).<br><br>> This field is required for partial refunds with 3x 4x Oney, Affirm, Afterpay, Atome, Clearpay, Klarna, Ratepay, Walley, and Zip. | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `merchantAccount` | `string` | Required | The merchant account that is used to process the payment. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `paymentPspReference` | `string` | Required | The [`pspReference`](https://docs.adyen.com/api-explorer/Checkout/latest/post/payments#responses-200-pspReference) of the payment to capture. | getPaymentPspReference(): string | setPaymentPspReference(string paymentPspReference): void |
| `platformChargebackLogic` | [`?PlatformChargebackLogic`](../../doc/models/platform-chargeback-logic.md) | Optional | Defines how to book chargebacks when using [Adyen for Platforms](https://docs.adyen.com/adyen-for-platforms-model). | getPlatformChargebackLogic(): ?PlatformChargebackLogic | setPlatformChargebackLogic(?PlatformChargebackLogic platformChargebackLogic): void |
| `pspReference` | `string` | Required | Adyen's 16-character reference associated with the capture request. | getPspReference(): string | setPspReference(string pspReference): void |
| `reference` | `?string` | Optional | Your reference for the capture request. | getReference(): ?string | setReference(?string reference): void |
| `splits` | [`?(Split[])`](../../doc/models/split.md) | Optional | An array of objects specifying how the amount should be split between accounts when using Adyen for Platforms. For more information, see how to process payments for [marketplaces](https://docs.adyen.com/marketplaces/split-payments) or [platforms](https://docs.adyen.com/platforms/online-payments/split-payments/). | getSplits(): ?array | setSplits(?array splits): void |
| `status` | `string` | Required, Constant | The status of your request. This will always have the value **received**.<br><br>**Value**: `'received'` | getStatus(): string | setStatus(string status): void |
| `subMerchants` | [`?(SubMerchantInfo[])`](../../doc/models/sub-merchant-info.md) | Optional | List of sub-merchants. | getSubMerchants(): ?array | setSubMerchants(?array subMerchants): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentCaptureResponseBuilder;
use AdyenLib\Models\Builders\Amount33Builder;
use AdyenLib\Models\Builders\LineItemBuilder;
use AdyenLib\Models\Builders\PlatformChargebackLogicBuilder;
use AdyenLib\Models\BehaviorEnum;
use AdyenLib\Models\Builders\SplitBuilder;
use AdyenLib\Models\Type11Enum;
use AdyenLib\Models\Builders\SplitAmountBuilder;
use AdyenLib\Models\Builders\SubMerchantInfoBuilder;
use AdyenLib\Models\Builders\BillingAddress4Builder;
use AdyenLib\Models\Builders\Amount32Builder;

$paymentCaptureResponse = PaymentCaptureResponseBuilder::init(
    Amount33Builder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount4',
    'paymentPspReference8',
    'pspReference4'
)
    ->lineItems(
        [
            LineItemBuilder::init()
                ->amountExcludingTax(38)
                ->amountIncludingTax(148)
                ->brand('brand6')
                ->color('color6')
                ->description('description2')
                ->build(),
            LineItemBuilder::init()
                ->amountExcludingTax(38)
                ->amountIncludingTax(148)
                ->brand('brand6')
                ->color('color6')
                ->description('description2')
                ->build()
        ]
    )
    ->platformChargebackLogic(
        PlatformChargebackLogicBuilder::init()
            ->behavior(BehaviorEnum::DEDUCTFROMONEBALANCEACCOUNT)
            ->costAllocationAccount('costAllocationAccount8')
            ->targetAccount('targetAccount6')
            ->build()
    )
    ->reference('reference0')
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
                ->build(),
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
                ->build(),
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
    ->subMerchants(
        [
            SubMerchantInfoBuilder::init()
                ->address(
                    BillingAddress4Builder::init(
                        'city6',
                        'country0',
                        'houseNumberOrName4',
                        'postalCode8',
                        'street6'
                    )
                        ->stateOrProvince('stateOrProvince4')
                        ->build()
                )
                ->amount(
                    Amount32Builder::init(
                        'currency2',
                        110
                    )->build()
                )
                ->email('email6')
                ->id('id0')
                ->mcc('mcc0')
                ->build(),
            SubMerchantInfoBuilder::init()
                ->address(
                    BillingAddress4Builder::init(
                        'city6',
                        'country0',
                        'houseNumberOrName4',
                        'postalCode8',
                        'street6'
                    )
                        ->stateOrProvince('stateOrProvince4')
                        ->build()
                )
                ->amount(
                    Amount32Builder::init(
                        'currency2',
                        110
                    )->build()
                )
                ->email('email6')
                ->id('id0')
                ->mcc('mcc0')
                ->build()
        ]
    )
    ->build();
```

