
# Payment Method Setup Info

## Structure

`PaymentMethodSetupInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accel` | [`?AccelInfo1`](../../doc/models/accel-info-1.md) | Optional | Details to provide if `type` is **accel**. | getAccel(): ?AccelInfo1 | setAccel(?AccelInfo1 accel): void |
| `affirm` | [`?AffirmInfo1`](../../doc/models/affirm-info-1.md) | Optional | Details to provide if `type` is **affirm**. | getAffirm(): ?AffirmInfo1 | setAffirm(?AffirmInfo1 affirm): void |
| `afterpayTouch` | [`?AfterpayTouchInfo1`](../../doc/models/afterpay-touch-info-1.md) | Optional | Details to provide if `type` is **afterpaytouch**. | getAfterpayTouch(): ?AfterpayTouchInfo1 | setAfterpayTouch(?AfterpayTouchInfo1 afterpayTouch): void |
| `alipayPlus` | [`?AlipayPlusInfo1`](../../doc/models/alipay-plus-info-1.md) | Optional | Details to provide if `type` is **alipay_plus**. | getAlipayPlus(): ?AlipayPlusInfo1 | setAlipayPlus(?AlipayPlusInfo1 alipayPlus): void |
| `amex` | [`?AmexInfo1`](../../doc/models/amex-info-1.md) | Optional | Details to provide if `type` is **amex**.<br>For merchants operating in Australia, New Zealand & Canada, JCB and American Express are automatically requested together. | getAmex(): ?AmexInfo1 | setAmex(?AmexInfo1 amex): void |
| `applePay` | [`?ApplePayInfo1`](../../doc/models/apple-pay-info-1.md) | Optional | Details to provide if `type` is **applepay**. | getApplePay(): ?ApplePayInfo1 | setApplePay(?ApplePayInfo1 applePay): void |
| `bcmc` | [`?BcmcInfo1`](../../doc/models/bcmc-info-1.md) | Optional | Details to provide if `type` is **bcmc** (Bancontact). | getBcmc(): ?BcmcInfo1 | setBcmc(?BcmcInfo1 bcmc): void |
| `businessLineId` | `?string` | Optional | The unique identifier of the business line. Required if you are a [platform model](https://docs.adyen.com/platforms). | getBusinessLineId(): ?string | setBusinessLineId(?string businessLineId): void |
| `carnet` | [`?CarnetInfo1`](../../doc/models/carnet-info-1.md) | Optional | Details to provide if `type` is **carnet**. | getCarnet(): ?CarnetInfo1 | setCarnet(?CarnetInfo1 carnet): void |
| `cartesBancaires` | [`?CartesBancairesInfo1`](../../doc/models/cartes-bancaires-info-1.md) | Optional | Details to provide if `type` is **cartebancaire**. | getCartesBancaires(): ?CartesBancairesInfo1 | setCartesBancaires(?CartesBancairesInfo1 cartesBancaires): void |
| `clearpay` | [`?ClearpayInfo1`](../../doc/models/clearpay-info-1.md) | Optional | Details to provide if `type` is **clearpay**. | getClearpay(): ?ClearpayInfo1 | setClearpay(?ClearpayInfo1 clearpay): void |
| `countries` | `?(string[])` | Optional | The list of countries where a payment method is available. By default, all countries supported by the payment method. | getCountries(): ?array | setCountries(?array countries): void |
| `cup` | [`?GenericPmWithTdiInfo1`](../../doc/models/generic-pm-with-tdi-info-1.md) | Optional | Details to provide if `type` is **cup** (China Union Pay). | getCup(): ?GenericPmWithTdiInfo1 | setCup(?GenericPmWithTdiInfo1 cup): void |
| `currencies` | `?(string[])` | Optional | The list of currencies that a payment method supports. By default, all currencies supported by the payment method. | getCurrencies(): ?array | setCurrencies(?array currencies): void |
| `customRoutingFlags` | `?(string[])` | Optional | The list of custom routing flags to route payment to the intended acquirer. | getCustomRoutingFlags(): ?array | setCustomRoutingFlags(?array customRoutingFlags): void |
| `diners` | [`?DinersInfo1`](../../doc/models/diners-info-1.md) | Optional | Details to provide if `type` is **diners**.<br>For merchants operating in Japan, Diners payments are processed through the JCB network. This means that you must include [JCB-specific fields](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/(merchantId)/paymentMethodSettings/(paymentMethodId)#request-jcb) in this object. | getDiners(): ?DinersInfo1 | setDiners(?DinersInfo1 diners): void |
| `discover` | [`?GenericPmWithTdiInfo2`](../../doc/models/generic-pm-with-tdi-info-2.md) | Optional | Details to provide if `type` is **discover**.<br>For merchants operating in Japan, request [Diners](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/(merchantId)/paymentMethodSettings/(paymentMethodId)#request-diners) payment method instead. Discover is automatically requested, together with Diners. | getDiscover(): ?GenericPmWithTdiInfo2 | setDiscover(?GenericPmWithTdiInfo2 discover): void |
| `eftDirectdebitCA` | [`?GenericPmWithTdiInfo3`](../../doc/models/generic-pm-with-tdi-info-3.md) | Optional | Details to provide if `type` is **eft_directdebit_CA** (EFT PAD). | getEftDirectdebitCA(): ?GenericPmWithTdiInfo3 | setEftDirectdebitCA(?GenericPmWithTdiInfo3 eftDirectdebitCA): void |
| `eftposAustralia` | [`?GenericPmWithTdiInfo4`](../../doc/models/generic-pm-with-tdi-info-4.md) | Optional | Details to provide if `type` is **eftpos_australia**. | getEftposAustralia(): ?GenericPmWithTdiInfo4 | setEftposAustralia(?GenericPmWithTdiInfo4 eftposAustralia): void |
| `girocard` | [`?GenericPmWithTdiInfo5`](../../doc/models/generic-pm-with-tdi-info-5.md) | Optional | Details to provide if `type` is **girocard**. | getGirocard(): ?GenericPmWithTdiInfo5 | setGirocard(?GenericPmWithTdiInfo5 girocard): void |
| `givex` | [`?GivexInfo1`](../../doc/models/givex-info-1.md) | Optional | Details to provide if `type` is **givex**. | getGivex(): ?GivexInfo1 | setGivex(?GivexInfo1 givex): void |
| `googlePay` | [`?GooglePayInfo1`](../../doc/models/google-pay-info-1.md) | Optional | Details to provide if `type` is **googlepay**. | getGooglePay(): ?GooglePayInfo1 | setGooglePay(?GooglePayInfo1 googlePay): void |
| `ideal` | [`?GenericPmWithTdiInfo6`](../../doc/models/generic-pm-with-tdi-info-6.md) | Optional | Details to provide if `type` is **ideal**. | getIdeal(): ?GenericPmWithTdiInfo6 | setIdeal(?GenericPmWithTdiInfo6 ideal): void |
| `interacCard` | [`?GenericPmWithTdiInfo7`](../../doc/models/generic-pm-with-tdi-info-7.md) | Optional | Details to provide if `type` is **interac_card**. | getInteracCard(): ?GenericPmWithTdiInfo7 | setInteracCard(?GenericPmWithTdiInfo7 interacCard): void |
| `jcb` | [`?JCBInfo1`](../../doc/models/jcb-info-1.md) | Optional | Details to provide if `type` is **jcb**.<br>For merchants operating in Japan, `midNumber`, `reuseMidNumber`, and `serviceLevel` fields are required.<br>For merchants operating outside of Japan, these fields are not required.<br>For merchants operating in Australia, New Zealand & Canada, JCB and American Express are automatically requested together. | getJcb(): ?JCBInfo1 | setJcb(?JCBInfo1 jcb): void |
| `klarna` | [`?KlarnaInfo1`](../../doc/models/klarna-info-1.md) | Optional | Details to provide if `type` is **klarna** or its variant.<br><br>You can use the following payment method `type` values for Klarna:<br><br>* **klarna**: Klarna Pay Later<br>* **klarna_account**: Klarna Pay over time<br>* **klarna_paynow**: Klarna Pay now<br>* **klarna_b2b**: [Billie via Klarna](https://docs.adyen.com/payment-methods/klarna/billie) | getKlarna(): ?KlarnaInfo1 | setKlarna(?KlarnaInfo1 klarna): void |
| `maestro` | [`?GenericPmWithTdiInfo8`](../../doc/models/generic-pm-with-tdi-info-8.md) | Optional | Details to provide if `type` is **maestro**.<br>In the US, `maestro` is not supported; use `maestro_usa` instead. | getMaestro(): ?GenericPmWithTdiInfo8 | setMaestro(?GenericPmWithTdiInfo8 maestro): void |
| `maestroUsa` | [`?GenericPmWithTdiInfo9`](../../doc/models/generic-pm-with-tdi-info-9.md) | Optional | Details to provide if `type` is **maestro_usa**.<br>Only for Maestro USA, otherwise use `maestro`. | getMaestroUsa(): ?GenericPmWithTdiInfo9 | setMaestroUsa(?GenericPmWithTdiInfo9 maestroUsa): void |
| `mc` | [`?GenericPmWithTdiInfo10`](../../doc/models/generic-pm-with-tdi-info-10.md) | Optional | Details to provide if `type` is **mc**. | getMc(): ?GenericPmWithTdiInfo10 | setMc(?GenericPmWithTdiInfo10 mc): void |
| `mealVoucherFR` | [`?MealVoucherFRInfo1`](../../doc/models/meal-voucher-fr-info-1.md) | Optional | Details to provide if `type` is **mealVoucher_FR**. | getMealVoucherFR(): ?MealVoucherFRInfo1 | setMealVoucherFR(?MealVoucherFRInfo1 mealVoucherFR): void |
| `nyce` | [`?NyceInfo1`](../../doc/models/nyce-info-1.md) | Optional | Details to provide if `type` is **nyce**. | getNyce(): ?NyceInfo1 | setNyce(?NyceInfo1 nyce): void |
| `paybybankPlaid` | [`?PayByBankPlaidInfo1`](../../doc/models/pay-by-bank-plaid-info-1.md) | Optional | Details to provide if `type` is **paybybank_plaid**. | getPaybybankPlaid(): ?PayByBankPlaidInfo1 | setPaybybankPlaid(?PayByBankPlaidInfo1 paybybankPlaid): void |
| `payme` | [`?PayMeInfo1`](../../doc/models/pay-me-info-1.md) | Optional | Details to provide if `type` is **payme**. | getPayme(): ?PayMeInfo1 | setPayme(?PayMeInfo1 payme): void |
| `paypal` | [`?PayPalInfo1`](../../doc/models/pay-pal-info-1.md) | Optional | Details to provide if `type` is **paypal**. | getPaypal(): ?PayPalInfo1 | setPaypal(?PayPalInfo1 paypal): void |
| `payto` | [`?PayToInfo1`](../../doc/models/pay-to-info-1.md) | Optional | Details to provide if `type` is **payto**. | getPayto(): ?PayToInfo1 | setPayto(?PayToInfo1 payto): void |
| `pulse` | [`?PulseInfo2`](../../doc/models/pulse-info-2.md) | Optional | Details to provide if `type` is **pulse**. | getPulse(): ?PulseInfo2 | setPulse(?PulseInfo2 pulse): void |
| `reference` | `?string` | Optional | Your reference for the payment method. Supported characters a-z, A-Z, 0-9.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `sepadirectdebit` | [`?SepaDirectDebitInfo2`](../../doc/models/sepa-direct-debit-info-2.md) | Optional | Details to provide if `type` is **sepadirectdebit**. | getSepadirectdebit(): ?SepaDirectDebitInfo2 | setSepadirectdebit(?SepaDirectDebitInfo2 sepadirectdebit): void |
| `shopperInteraction` | [`?string(ShopperInteraction1Enum)`](../../doc/models/shopper-interaction-1-enum.md) | Optional | The sales channel. Required if:<br><br>- The merchant account does not have a sales channel.<br>- `type` is **alipay**.<br><br>When you provide this field, it overrides the default sales channel set on the merchant account.<br><br>Possible values: **eCommerce**, **pos**, **contAuth**, and **moto**. | getShopperInteraction(): ?string | setShopperInteraction(?string shopperInteraction): void |
| `sodexo` | [`?SodexoInfo2`](../../doc/models/sodexo-info-2.md) | Optional | Details to provide if `type` is **sodexo**. | getSodexo(): ?SodexoInfo2 | setSodexo(?SodexoInfo2 sodexo): void |
| `sofort` | [`?SofortInfo2`](../../doc/models/sofort-info-2.md) | Optional | Sofort details. | getSofort(): ?SofortInfo2 | setSofort(?SofortInfo2 sofort): void |
| `star` | [`?StarInfo2`](../../doc/models/star-info-2.md) | Optional | Details to provide if `type` is **star**. | getStar(): ?StarInfo2 | setStar(?StarInfo2 star): void |
| `storeIds` | `?(string[])` | Optional | The unique identifier of the store for which to configure the payment method, if any. | getStoreIds(): ?array | setStoreIds(?array storeIds): void |
| `svs` | [`?SvsInfo2`](../../doc/models/svs-info-2.md) | Optional | Details to provide if `type` is **svs**. | getSvs(): ?SvsInfo2 | setSvs(?SvsInfo2 svs): void |
| `swish` | [`?SwishInfo2`](../../doc/models/swish-info-2.md) | Optional | Details to provide if `type` is **swish**.<br><br>- This field is required only if you have a contract with Swish. Swish handles settlement directly with you (not through Adyen).<br>- If not specified then it's assumed that you are using Adyen's contract with Swish.You don't have a direct relationship with Swish. | getSwish(): ?SwishInfo2 | setSwish(?SwishInfo2 swish): void |
| `ticket` | [`?TicketInfo2`](../../doc/models/ticket-info-2.md) | Optional | Details to provide if `type` is **ticket** (Edenred Brazil). | getTicket(): ?TicketInfo2 | setTicket(?TicketInfo2 ticket): void |
| `twint` | [`?TwintInfo2`](../../doc/models/twint-info-2.md) | Optional | Details to provide if `type` is **twint**. | getTwint(): ?TwintInfo2 | setTwint(?TwintInfo2 twint): void |
| `type` | [`string(Type59Enum)`](../../doc/models/type-59-enum.md) | Required | Payment method [variant](https://docs.adyen.com/development-resources/paymentmethodvariant#management-api). | getType(): string | setType(string type): void |
| `valuelink` | [`?ValuelinkInfo2`](../../doc/models/valuelink-info-2.md) | Optional | Details to provide if `type` is **valuelink**. | getValuelink(): ?ValuelinkInfo2 | setValuelink(?ValuelinkInfo2 valuelink): void |
| `vipps` | [`?VippsInfo2`](../../doc/models/vipps-info-2.md) | Optional | Details to provide if `type` is **vipps**. | getVipps(): ?VippsInfo2 | setVipps(?VippsInfo2 vipps): void |
| `visa` | [`?GenericPmWithTdiInfo11`](../../doc/models/generic-pm-with-tdi-info-11.md) | Optional | Details to provide if `type` is **visa**. | getVisa(): ?GenericPmWithTdiInfo11 | setVisa(?GenericPmWithTdiInfo11 visa): void |
| `wechatpay` | [`?WeChatPayInfo2`](../../doc/models/we-chat-pay-info-2.md) | Optional | Details to provide if `type` is **wechatpay**. | getWechatpay(): ?WeChatPayInfo2 | setWechatpay(?WeChatPayInfo2 wechatpay): void |
| `wechatpayPos` | [`?WeChatPayPosInfo2`](../../doc/models/we-chat-pay-pos-info-2.md) | Optional | Details to provide if `type` is **wechatpay_pos**. | getWechatpayPos(): ?WeChatPayPosInfo2 | setWechatpayPos(?WeChatPayPosInfo2 wechatpayPos): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentMethodSetupInfoBuilder;
use AdyenLib\Models\Type59Enum;
use AdyenLib\Models\Builders\AccelInfo1Builder;
use AdyenLib\Models\ProcessingTypeEnum;
use AdyenLib\Models\Builders\TransactionDescriptionInfo1Builder;
use AdyenLib\Models\Type8Enum;
use AdyenLib\Models\Builders\AffirmInfo1Builder;
use AdyenLib\Models\Builders\AfterpayTouchInfo1Builder;
use AdyenLib\Models\Builders\AlipayPlusInfo1Builder;
use AdyenLib\Models\Builders\AmexInfo1Builder;
use AdyenLib\Models\ServiceLevelEnum;

$paymentMethodSetupInfo = PaymentMethodSetupInfoBuilder::init(
    Type59Enum::ABRAPETITE
)
    ->accel(
        AccelInfo1Builder::init(
            ProcessingTypeEnum::BILLPAY
        )
            ->transactionDescription(
                TransactionDescriptionInfo1Builder::init()
                    ->doingBusinessAsName('doingBusinessAsName0')
                    ->type(Type8Enum::FIXED)
                    ->build()
            )
            ->build()
    )
    ->affirm(
        AffirmInfo1Builder::init(
            'supportEmail2'
        )
            ->pricePlan('pricePlan8')
            ->build()
    )
    ->afterpayTouch(
        AfterpayTouchInfo1Builder::init(
            'supportUrl4'
        )
            ->supportEmail('supportEmail8')
            ->build()
    )
    ->alipayPlus(
        AlipayPlusInfo1Builder::init()
            ->settlementCurrencyCode('settlementCurrencyCode0')
            ->build()
    )
    ->amex(
        AmexInfo1Builder::init(
            ServiceLevelEnum::GATEWAYCONTRACT
        )
            ->midNumber('midNumber4')
            ->reuseMidNumber(false)
            ->build()
    )
    ->build();
```

