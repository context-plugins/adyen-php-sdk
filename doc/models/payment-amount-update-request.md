
# Payment Amount Update Request

## Structure

`PaymentAmountUpdateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adjustAuthType` | [`?string(AdjustAuthTypeEnum)`](../../doc/models/adjust-auth-type-enum.md) | Optional | The type of adjustment. Possible values:<br><br>* **cardholderInitiatedTransaction**<br><br>* **merchantInitiatedTransaction** | getAdjustAuthType(): ?string | setAdjustAuthType(?string adjustAuthType): void |
| `adjustAuthorisationData` | `?string` | Optional | The required data to make a [synchronous authorization adjustment](https://docs.adyen.com/online-payments/adjust-authorisation). Pass the corresponding value from the `/payments` response or webhook message. | getAdjustAuthorisationData(): ?string | setAdjustAuthorisationData(?string adjustAuthorisationData): void |
| `amount` | [`Amount29`](../../doc/models/amount-29.md) | Required | The updated amount. The `currency` must match the currency used in authorisation. | getAmount(): Amount29 | setAmount(Amount29 amount): void |
| `applicationInfo` | [`?ApplicationInfo`](../../doc/models/application-info.md) | Optional | Information about your application. For more details, see [Building Adyen solutions](https://docs.adyen.com/development-resources/building-adyen-solutions). | getApplicationInfo(): ?ApplicationInfo | setApplicationInfo(?ApplicationInfo applicationInfo): void |
| `industryUsage` | [`?string(IndustryUsage1Enum)`](../../doc/models/industry-usage-1-enum.md) | Optional | The reason for the amount update. Possible values:<br><br>* **delayedCharge**<br>* **noShow**<br>* **installment** | getIndustryUsage(): ?string | setIndustryUsage(?string industryUsage): void |
| `lineItems` | [`?(LineItem[])`](../../doc/models/line-item.md) | Optional | Price and product information of the refunded items, required for [partial refunds](https://docs.adyen.com/online-payments/refund#refund-a-payment).<br><br>> This field is required for partial refunds with 3x 4x Oney, Affirm, Afterpay, Atome, Clearpay, Klarna, Ratepay, Walley, and Zip. | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `merchantAccount` | `string` | Required | The merchant account that is used to process the payment. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `mpiData` | [`?ThreeDSecureData3`](../../doc/models/three-d-secure-data-3.md) | Optional | Authentication data from a [merchant plug-in (MPI)](https://en.wikipedia.org/wiki/Merchant_plug-in) like Mastercard SecureCode, Visa Secure, or Cartes Bancaires. Required for cardholder-initiated transaction (CIT) adjustments. | getMpiData(): ?ThreeDSecureData3 | setMpiData(?ThreeDSecureData3 mpiData): void |
| `reference` | `?string` | Optional | Your reference for the amount update request. Maximum length: 80 characters. | getReference(): ?string | setReference(?string reference): void |
| `splits` | [`?(Split[])`](../../doc/models/split.md) | Optional | An array of objects specifying how the amount should be split between accounts when using Adyen for Platforms. For more information, see how to process payments for [marketplaces](https://docs.adyen.com/marketplaces/process-payments) or [platforms](https://docs.adyen.com/platforms/process-payments). | getSplits(): ?array | setSplits(?array splits): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentAmountUpdateRequestBuilder;
use AdyenLib\Models\Builders\Amount29Builder;
use AdyenLib\Models\AdjustAuthTypeEnum;
use AdyenLib\Models\Builders\ApplicationInfoBuilder;
use AdyenLib\Models\Builders\CommonField4Builder;
use AdyenLib\Models\Builders\CommonField1Builder;
use AdyenLib\Models\Builders\ExternalPlatformBuilder;
use AdyenLib\Models\Builders\CommonField2Builder;
use AdyenLib\Models\Builders\MerchantDeviceBuilder;
use AdyenLib\Models\IndustryUsage1Enum;
use AdyenLib\Models\Builders\LineItemBuilder;

$paymentAmountUpdateRequest = PaymentAmountUpdateRequestBuilder::init(
    Amount29Builder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount8'
)
    ->adjustAuthType(AdjustAuthTypeEnum::CARDHOLDERINITIATEDTRANSACTION)
    ->adjustAuthorisationData('adjustAuthorisationData4')
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
    ->industryUsage(IndustryUsage1Enum::INSTALLMENT)
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
    ->build();
```

