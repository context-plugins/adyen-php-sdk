
# Management Payment Method

## Structure

`ManagementPaymentMethod`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accel` | [`?AccelResponseInfo1`](../../doc/models/accel-response-info-1.md) | Optional | **accel** details | getAccel(): ?AccelResponseInfo1 | setAccel(?AccelResponseInfo1 accel): void |
| `affirm` | [`?AffirmResponseInfo1`](../../doc/models/affirm-response-info-1.md) | Optional | *affirm** details | getAffirm(): ?AffirmResponseInfo1 | setAffirm(?AffirmResponseInfo1 affirm): void |
| `afterpayTouch` | [`?AfterpayTouchResponseInfo1`](../../doc/models/afterpay-touch-response-info-1.md) | Optional | **afterpaytouch** details | getAfterpayTouch(): ?AfterpayTouchResponseInfo1 | setAfterpayTouch(?AfterpayTouchResponseInfo1 afterpayTouch): void |
| `alipayPlus` | [`?AlipayPlusResponseInfo1`](../../doc/models/alipay-plus-response-info-1.md) | Optional | **alipay_plus** details | getAlipayPlus(): ?AlipayPlusResponseInfo1 | setAlipayPlus(?AlipayPlusResponseInfo1 alipayPlus): void |
| `allowed` | `?bool` | Optional | Indicates whether receiving payments is allowed. This value is set to **true** by Adyen after screening your merchant account. | getAllowed(): ?bool | setAllowed(?bool allowed): void |
| `amex` | [`?AmexResponseInfo1`](../../doc/models/amex-response-info-1.md) | Optional | **amex** details | getAmex(): ?AmexResponseInfo1 | setAmex(?AmexResponseInfo1 amex): void |
| `applePay` | [`?ApplePayResponseInfo1`](../../doc/models/apple-pay-response-info-1.md) | Optional | **applepay** details | getApplePay(): ?ApplePayResponseInfo1 | setApplePay(?ApplePayResponseInfo1 applePay): void |
| `associatedPaymentMethods` | [`?(AssociatedPaymentMethod[])`](../../doc/models/associated-payment-method.md) | Optional | Payment methods that were also updated as part of an associated transition. | getAssociatedPaymentMethods(): ?array | setAssociatedPaymentMethods(?array associatedPaymentMethods): void |
| `bcmc` | [`?BcmcResponseInfo1`](../../doc/models/bcmc-response-info-1.md) | Optional | **bcmc** (Bancontact) details | getBcmc(): ?BcmcResponseInfo1 | setBcmc(?BcmcResponseInfo1 bcmc): void |
| `businessLineId` | `?string` | Optional | The unique identifier of the business line. Required if you are a [platform model](https://docs.adyen.com/platforms). | getBusinessLineId(): ?string | setBusinessLineId(?string businessLineId): void |
| `carnet` | [`?CarnetResponseInfo1`](../../doc/models/carnet-response-info-1.md) | Optional | **carnet** details | getCarnet(): ?CarnetResponseInfo1 | setCarnet(?CarnetResponseInfo1 carnet): void |
| `cartesBancaires` | [`?CartesBancairesResponseInfo1`](../../doc/models/cartes-bancaires-response-info-1.md) | Optional | **cartesbancaire** details | getCartesBancaires(): ?CartesBancairesResponseInfo1 | setCartesBancaires(?CartesBancairesResponseInfo1 cartesBancaires): void |
| `clearpay` | [`?ClearpayResponseInfo1`](../../doc/models/clearpay-response-info-1.md) | Optional | **clearpay** details | getClearpay(): ?ClearpayResponseInfo1 | setClearpay(?ClearpayResponseInfo1 clearpay): void |
| `countries` | `?(string[])` | Optional | The list of countries where a payment method is available. By default, all countries supported by the payment method. | getCountries(): ?array | setCountries(?array countries): void |
| `cup` | [`?CupResponseInfo1`](../../doc/models/cup-response-info-1.md) | Optional | **cup** (China Union Pay) details | getCup(): ?CupResponseInfo1 | setCup(?CupResponseInfo1 cup): void |
| `currencies` | `?(string[])` | Optional | The list of currencies that a payment method supports. By default, all currencies supported by the payment method. | getCurrencies(): ?array | setCurrencies(?array currencies): void |
| `customRoutingFlags` | `?(string[])` | Optional | The list of custom routing flags to route payment to the intended acquirer. | getCustomRoutingFlags(): ?array | setCustomRoutingFlags(?array customRoutingFlags): void |
| `diners` | [`?DinersResponseInfo1`](../../doc/models/diners-response-info-1.md) | Optional | **diners** details | getDiners(): ?DinersResponseInfo1 | setDiners(?DinersResponseInfo1 diners): void |
| `discover` | [`?DiscoverResponseInfo1`](../../doc/models/discover-response-info-1.md) | Optional | **discover**. details | getDiscover(): ?DiscoverResponseInfo1 | setDiscover(?DiscoverResponseInfo1 discover): void |
| `eftDirectdebitCA` | [`?EFTDirectDebitCAResponseInfo1`](../../doc/models/eft-direct-debit-ca-response-info-1.md) | Optional | **eft_directdebit_CA** (EFT PAD) details | getEftDirectdebitCA(): ?EFTDirectDebitCAResponseInfo1 | setEftDirectdebitCA(?EFTDirectDebitCAResponseInfo1 eftDirectdebitCA): void |
| `eftposAustralia` | [`?EftPosAustraliaResponseInfo1`](../../doc/models/eft-pos-australia-response-info-1.md) | Optional | **eftpos_australia** details | getEftposAustralia(): ?EftPosAustraliaResponseInfo1 | setEftposAustralia(?EftPosAustraliaResponseInfo1 eftposAustralia): void |
| `enabled` | `?bool` | Optional | Indicates whether the payment method is enabled (**true**) or disabled (**false**). | getEnabled(): ?bool | setEnabled(?bool enabled): void |
| `girocard` | [`?GirocardResponseInfo1`](../../doc/models/girocard-response-info-1.md) | Optional | **girocard** details | getGirocard(): ?GirocardResponseInfo1 | setGirocard(?GirocardResponseInfo1 girocard): void |
| `givex` | [`?GivexResponseInfo1`](../../doc/models/givex-response-info-1.md) | Optional | **givex** details | getGivex(): ?GivexResponseInfo1 | setGivex(?GivexResponseInfo1 givex): void |
| `googlePay` | [`?GooglePayResponseInfo1`](../../doc/models/google-pay-response-info-1.md) | Optional | **googlepay** details | getGooglePay(): ?GooglePayResponseInfo1 | setGooglePay(?GooglePayResponseInfo1 googlePay): void |
| `id` | `string` | Required | The identifier of the resource. | getId(): string | setId(string id): void |
| `ideal` | [`?IdealResponseInfo1`](../../doc/models/ideal-response-info-1.md) | Optional | **ideal** details | getIdeal(): ?IdealResponseInfo1 | setIdeal(?IdealResponseInfo1 ideal): void |
| `interacCard` | [`?InteracCardResponseInfo1`](../../doc/models/interac-card-response-info-1.md) | Optional | **interac_card** details | getInteracCard(): ?InteracCardResponseInfo1 | setInteracCard(?InteracCardResponseInfo1 interacCard): void |
| `jcb` | [`?JCBResponseInfo1`](../../doc/models/jcb-response-info-1.md) | Optional | **jcb** details | getJcb(): ?JCBResponseInfo1 | setJcb(?JCBResponseInfo1 jcb): void |
| `klarna` | [`?KlarnaResponseInfo1`](../../doc/models/klarna-response-info-1.md) | Optional | **klarna** or its variant details | getKlarna(): ?KlarnaResponseInfo1 | setKlarna(?KlarnaResponseInfo1 klarna): void |
| `maestro` | [`?MaestroResponseInfo1`](../../doc/models/maestro-response-info-1.md) | Optional | **maestro** details | getMaestro(): ?MaestroResponseInfo1 | setMaestro(?MaestroResponseInfo1 maestro): void |
| `maestroUsa` | [`?MaestroUSAResponseInfo1`](../../doc/models/maestro-usa-response-info-1.md) | Optional | Details to provide if `type` is **maestro_usa** details | getMaestroUsa(): ?MaestroUSAResponseInfo1 | setMaestroUsa(?MaestroUSAResponseInfo1 maestroUsa): void |
| `mc` | [`?MCResponseInfo1`](../../doc/models/mc-response-info-1.md) | Optional | **mc** details | getMc(): ?MCResponseInfo1 | setMc(?MCResponseInfo1 mc): void |
| `mealVoucherFR` | [`?MealVoucherFRResponseInfo1`](../../doc/models/meal-voucher-fr-response-info-1.md) | Optional | **mealVoucher_FR** details | getMealVoucherFR(): ?MealVoucherFRResponseInfo1 | setMealVoucherFR(?MealVoucherFRResponseInfo1 mealVoucherFR): void |
| `nyce` | [`?NyceResponseInfo1`](../../doc/models/nyce-response-info-1.md) | Optional | **nyce** details | getNyce(): ?NyceResponseInfo1 | setNyce(?NyceResponseInfo1 nyce): void |
| `paybybankPlaid` | [`?PayByBankPlaidResponseInfo1`](../../doc/models/pay-by-bank-plaid-response-info-1.md) | Optional | **paybybank_plaid** details | getPaybybankPlaid(): ?PayByBankPlaidResponseInfo1 | setPaybybankPlaid(?PayByBankPlaidResponseInfo1 paybybankPlaid): void |
| `payme` | [`?PayMeResponseInfo1`](../../doc/models/pay-me-response-info-1.md) | Optional | **payme** details | getPayme(): ?PayMeResponseInfo1 | setPayme(?PayMeResponseInfo1 payme): void |
| `paypal` | [`?PayPalResponseInfo1`](../../doc/models/pay-pal-response-info-1.md) | Optional | **paypal** details | getPaypal(): ?PayPalResponseInfo1 | setPaypal(?PayPalResponseInfo1 paypal): void |
| `payto` | [`?PayToResponseInfo1`](../../doc/models/pay-to-response-info-1.md) | Optional | **payto** details | getPayto(): ?PayToResponseInfo1 | setPayto(?PayToResponseInfo1 payto): void |
| `pulse` | [`?PulseResponseInfo2`](../../doc/models/pulse-response-info-2.md) | Optional | **pulse** details | getPulse(): ?PulseResponseInfo2 | setPulse(?PulseResponseInfo2 pulse): void |
| `reference` | `?string` | Optional | Your reference for the payment method. Supported characters a-z, A-Z, 0-9.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `sepadirectdebit` | [`?SepaDirectDebitResponseInfo2`](../../doc/models/sepa-direct-debit-response-info-2.md) | Optional | **sepadirectdebit** details | getSepadirectdebit(): ?SepaDirectDebitResponseInfo2 | setSepadirectdebit(?SepaDirectDebitResponseInfo2 sepadirectdebit): void |
| `shopperInteraction` | `?string` | Optional | The sales channel. | getShopperInteraction(): ?string | setShopperInteraction(?string shopperInteraction): void |
| `sodexo` | [`?SodexoResponseInfo2`](../../doc/models/sodexo-response-info-2.md) | Optional | **sodexo** details | getSodexo(): ?SodexoResponseInfo2 | setSodexo(?SodexoResponseInfo2 sodexo): void |
| `sofort` | [`?SofortResponseInfo2`](../../doc/models/sofort-response-info-2.md) | Optional | Sofort details. | getSofort(): ?SofortResponseInfo2 | setSofort(?SofortResponseInfo2 sofort): void |
| `star` | [`?StarResponseInfo2`](../../doc/models/star-response-info-2.md) | Optional | **star** details | getStar(): ?StarResponseInfo2 | setStar(?StarResponseInfo2 star): void |
| `storeIds` | `?(string[])` | Optional | The unique identifier of the store for which to configure the payment method, if any. | getStoreIds(): ?array | setStoreIds(?array storeIds): void |
| `svs` | [`?SvsResponseInfo2`](../../doc/models/svs-response-info-2.md) | Optional | **svs** details | getSvs(): ?SvsResponseInfo2 | setSvs(?SvsResponseInfo2 svs): void |
| `swish` | [`?SwishResponseInfo2`](../../doc/models/swish-response-info-2.md) | Optional | **swish** or its variant details | getSwish(): ?SwishResponseInfo2 | setSwish(?SwishResponseInfo2 swish): void |
| `ticket` | [`?TicketResponseInfo2`](../../doc/models/ticket-response-info-2.md) | Optional | **ticket** (Edenred Brazil) details | getTicket(): ?TicketResponseInfo2 | setTicket(?TicketResponseInfo2 ticket): void |
| `twint` | [`?TwintResponseInfo2`](../../doc/models/twint-response-info-2.md) | Optional | **twint** details | getTwint(): ?TwintResponseInfo2 | setTwint(?TwintResponseInfo2 twint): void |
| `type` | `?string` | Optional | Payment method [variant](https://docs.adyen.com/development-resources/paymentmethodvariant#management-api). | getType(): ?string | setType(?string type): void |
| `valuelink` | [`?ValuelinkResponseInfo2`](../../doc/models/valuelink-response-info-2.md) | Optional | **valuelink** details | getValuelink(): ?ValuelinkResponseInfo2 | setValuelink(?ValuelinkResponseInfo2 valuelink): void |
| `verificationStatus` | [`?string(VerificationStatusEnum)`](../../doc/models/verification-status-enum.md) | Optional | Payment method status. Possible values:<br><br>* **valid**<br>* **pending**<br>* **invalid**<br>* **rejected** | getVerificationStatus(): ?string | setVerificationStatus(?string verificationStatus): void |
| `vipps` | [`?VippsResponseInfo2`](../../doc/models/vipps-response-info-2.md) | Optional | **vipps** details | getVipps(): ?VippsResponseInfo2 | setVipps(?VippsResponseInfo2 vipps): void |
| `visa` | [`?VisaResponseInfo2`](../../doc/models/visa-response-info-2.md) | Optional | **visa** details | getVisa(): ?VisaResponseInfo2 | setVisa(?VisaResponseInfo2 visa): void |
| `wechatpay` | [`?WeChatPayResponseInfo2`](../../doc/models/we-chat-pay-response-info-2.md) | Optional | **wechatpay** details | getWechatpay(): ?WeChatPayResponseInfo2 | setWechatpay(?WeChatPayResponseInfo2 wechatpay): void |
| `wechatpayPos` | [`?WeChatPayPosResponseInfo2`](../../doc/models/we-chat-pay-pos-response-info-2.md) | Optional | **wechatpay_pos** details | getWechatpayPos(): ?WeChatPayPosResponseInfo2 | setWechatpayPos(?WeChatPayPosResponseInfo2 wechatpayPos): void |

## Example

```php
use AdyenLib\Models\Builders\ManagementPaymentMethodBuilder;
use AdyenLib\Models\Builders\AccelResponseInfo1Builder;
use AdyenLib\Models\ProcessingTypeEnum;
use AdyenLib\Models\Builders\TransactionDescriptionResponseInfo1Builder;
use AdyenLib\Models\Type8Enum;
use AdyenLib\Models\Builders\AffirmResponseInfo1Builder;
use AdyenLib\Models\Builders\AfterpayTouchResponseInfo1Builder;
use AdyenLib\Models\Builders\AlipayPlusResponseInfo1Builder;

$managementPaymentMethod = ManagementPaymentMethodBuilder::init(
    'id6'
)
    ->accel(
        AccelResponseInfo1Builder::init()
            ->processingType(ProcessingTypeEnum::BILLPAY)
            ->transactionDescription(
                TransactionDescriptionResponseInfo1Builder::init()
                    ->doingBusinessAsName('doingBusinessAsName0')
                    ->type(Type8Enum::FIXED)
                    ->build()
            )
            ->build()
    )
    ->affirm(
        AffirmResponseInfo1Builder::init()
            ->publicApiKey('publicApiKey4')
            ->build()
    )
    ->afterpayTouch(
        AfterpayTouchResponseInfo1Builder::init()
            ->supportEmail('supportEmail8')
            ->supportUrl('supportUrl4')
            ->build()
    )
    ->alipayPlus(
        AlipayPlusResponseInfo1Builder::init()
            ->settlementCurrencyCode('settlementCurrencyCode0')
            ->build()
    )
    ->allowed(false)
    ->build();
```

