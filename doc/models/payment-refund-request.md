
# Payment Refund Request

## Structure

`PaymentRefundRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | [`Amount38`](../../doc/models/amount-38.md) | Required | The amount that you want to refund. The `currency` must match the currency used in authorisation, the `value` must be smaller than or equal to the authorised amount. | getAmount(): Amount38 | setAmount(Amount38 amount): void |
| `applicationInfo` | [`?ApplicationInfo`](../../doc/models/application-info.md) | Optional | Information about your application. For more details, see [Building Adyen solutions](https://docs.adyen.com/development-resources/building-adyen-solutions). | getApplicationInfo(): ?ApplicationInfo | setApplicationInfo(?ApplicationInfo applicationInfo): void |
| `capturePspReference` | `?string` | Optional | This is only available for PayPal refunds. The [`pspReference`](https://docs.adyen.com/api-explorer/Checkout/latest/post/payments#responses-200-pspReference) of the specific capture to refund. | getCapturePspReference(): ?string | setCapturePspReference(?string capturePspReference): void |
| `enhancedSchemeData` | [`?EnhancedSchemeData1`](../../doc/models/enhanced-scheme-data-1.md) | Optional | Enhanced scheme data that may be required for processing the payment. For example, airline information. | getEnhancedSchemeData(): ?EnhancedSchemeData1 | setEnhancedSchemeData(?EnhancedSchemeData1 enhancedSchemeData): void |
| `lineItems` | [`?(LineItem[])`](../../doc/models/line-item.md) | Optional | Price and product information of the refunded items, required for [partial refunds](https://docs.adyen.com/online-payments/refund#refund-a-payment).<br><br>> This field is required for partial refunds with 3x 4x Oney, Affirm, Afterpay, Atome, Clearpay, Klarna, Ratepay, Walley, and Zip. | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `merchantAccount` | `string` | Required | The merchant account that is used to process the payment. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `merchantRefundReason` | [`?string(MerchantRefundReasonEnum)`](../../doc/models/merchant-refund-reason-enum.md) | Optional | The reason for the refund request.<br><br>Possible values:<br><br>* **FRAUD**<br><br>* **CUSTOMER REQUEST**<br><br>* **RETURN**<br><br>* **DUPLICATE**<br><br>* **OTHER** | getMerchantRefundReason(): ?string | setMerchantRefundReason(?string merchantRefundReason): void |
| `reference` | `?string` | Optional | Your reference for the refund request. Maximum length: 80 characters. | getReference(): ?string | setReference(?string reference): void |
| `splits` | [`?(Split[])`](../../doc/models/split.md) | Optional | An array of objects specifying how the amount should be split between accounts when using Adyen for Platforms. For more information, see how to process payments for [marketplaces](https://docs.adyen.com/marketplaces/split-payments) or [platforms](https://docs.adyen.com/platforms/online-payments/split-payments/). | getSplits(): ?array | setSplits(?array splits): void |
| `store` | `?string` | Optional | The online store or [physical store](https://docs.adyen.com/point-of-sale/design-your-integration/determine-account-structure/#create-stores) that is processing the refund. This must be the same as the store name configured in your Customer Area.  Otherwise, you get an error and the refund fails. | getStore(): ?string | setStore(?string store): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentRefundRequestBuilder;
use AdyenLib\Models\Builders\Amount38Builder;
use AdyenLib\Models\Builders\ApplicationInfoBuilder;
use AdyenLib\Models\Builders\CommonField4Builder;
use AdyenLib\Models\Builders\CommonField1Builder;
use AdyenLib\Models\Builders\ExternalPlatformBuilder;
use AdyenLib\Models\Builders\CommonField2Builder;
use AdyenLib\Models\Builders\MerchantDeviceBuilder;
use AdyenLib\Models\Builders\EnhancedSchemeData1Builder;
use AdyenLib\Models\Builders\Airline1Builder;
use AdyenLib\Models\Builders\AgencyBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\CarRental1Builder;
use AdyenLib\Models\Builders\PickupInfoBuilder;
use AdyenLib\Models\RateTypeEnum;
use AdyenLib\Models\Builders\Healthcare2Builder;
use AdyenLib\Models\Builders\LevelTwoThree2Builder;
use AdyenLib\Models\Builders\Destination1Builder;
use AdyenLib\Models\Builders\ItemDetailLineBuilder;
use AdyenLib\Models\Builders\Lodging2Builder;
use AdyenLib\Models\Builders\Folio2Builder;
use AdyenLib\Models\Builders\LineItemBuilder;
use AdyenLib\Models\MerchantRefundReasonEnum;

$paymentRefundRequest = PaymentRefundRequestBuilder::init(
    Amount38Builder::init(
        'currency2',
        110
    )->build(),
    'merchantAccount0'
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
    ->capturePspReference('capturePspReference6')
    ->enhancedSchemeData(
        EnhancedSchemeData1Builder::init()
            ->airline(
                Airline1Builder::init(
                    'passengerName0'
                )
                    ->agency(
                        AgencyBuilder::init()
                            ->invoiceNumber('invoiceNumber6')
                            ->planName('planName6')
                            ->build()
                    )
                    ->boardingFee(160)
                    ->code('code0')
                    ->computerizedReservationSystem('computerizedReservationSystem4')
                    ->customerReferenceNumber('customerReferenceNumber6')
                    ->build()
            )
            ->carRental(
                CarRental1Builder::init(
                    'renterName2'
                )
                    ->customerServicePhoneNumber('customerServicePhoneNumber8')
                    ->noShow(false)
                    ->pickupInfo(
                        PickupInfoBuilder::init()
                            ->city('city4')
                            ->countryCode('countryCode8')
                            ->date(DateTimeHelper::fromSimpleDate('2016-03-13'))
                            ->stateOrProvince('stateOrProvince4')
                            ->build()
                    )
                    ->rateType(RateTypeEnum::DAILY)
                    ->rentalAgreementNumber('rentalAgreementNumber4')
                    ->build()
            )
            ->healthcare(
                Healthcare2Builder::init(
                    16
                )
                    ->dentalValue(132)
                    ->otherMedicalValue(150)
                    ->prescriptionValue(116)
                    ->visionPrescriptionValue(166)
                    ->build()
            )
            ->levelTwoThree(
                LevelTwoThree2Builder::init()
                    ->customerReferenceNumber('customerReferenceNumber0')
                    ->destination(
                        Destination1Builder::init()
                            ->countryCode('countryCode0')
                            ->postalCode('postalCode6')
                            ->stateOrProvince('stateOrProvince2')
                            ->build()
                    )
                    ->dutyAmount(234)
                    ->freightAmount(136)
                    ->itemDetailLines(
                        [
                            ItemDetailLineBuilder::init()
                                ->commodityCode('commodityCode4')
                                ->description('description8')
                                ->discountAmount(220)
                                ->productCode('productCode0')
                                ->quantity(184)
                                ->build()
                        ]
                    )
                    ->build()
            )
            ->lodging(
                Lodging2Builder::init()
                    ->checkInDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
                    ->checkOutDate(DateTimeHelper::fromSimpleDate('2016-03-13'))
                    ->customerServicePhoneNumber('customerServicePhoneNumber6')
                    ->fireSafetyCompliance(false)
                    ->folio(
                        Folio2Builder::init()
                            ->cashAdvances(122)
                            ->number('number8')
                            ->build()
                    )
                    ->build()
            )
            ->build()
    )
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
    ->merchantRefundReason(MerchantRefundReasonEnum::DUPLICATE)
    ->build();
```

