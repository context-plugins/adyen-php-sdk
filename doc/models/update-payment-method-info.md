
# Update Payment Method Info

## Structure

`UpdatePaymentMethodInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accel` | [`?AccelUpdateInfo1`](../../doc/models/accel-update-info-1.md) | Optional | Details to provide if `type` is **accel**. | getAccel(): ?AccelUpdateInfo1 | setAccel(?AccelUpdateInfo1 accel): void |
| `affirm` | [`?AffirmUpdateInfo1`](../../doc/models/affirm-update-info-1.md) | Optional | Details to provide if `type` is **affirm**. | getAffirm(): ?AffirmUpdateInfo1 | setAffirm(?AffirmUpdateInfo1 affirm): void |
| `bcmc` | [`?BcmcUpdateInfo1`](../../doc/models/bcmc-update-info-1.md) | Optional | Details to provide if `type` is **bcmc** (Bancontact). | getBcmc(): ?BcmcUpdateInfo1 | setBcmc(?BcmcUpdateInfo1 bcmc): void |
| `carnet` | [`?GenericPmWithTdiUpdateInfo1`](../../doc/models/generic-pm-with-tdi-update-info-1.md) | Optional | Details to provide if `type` is **carnet**. | getCarnet(): ?GenericPmWithTdiUpdateInfo1 | setCarnet(?GenericPmWithTdiUpdateInfo1 carnet): void |
| `cartesBancaires` | [`?CartesBancairesUpdateInfo1`](../../doc/models/cartes-bancaires-update-info-1.md) | Optional | Details to provide if `type` is **cartebancaire**. | getCartesBancaires(): ?CartesBancairesUpdateInfo1 | setCartesBancaires(?CartesBancairesUpdateInfo1 cartesBancaires): void |
| `cashapp` | [`?CashAppUpdateInfo1`](../../doc/models/cash-app-update-info-1.md) | Optional | Details to provide if `type` is **cashapp**. | getCashapp(): ?CashAppUpdateInfo1 | setCashapp(?CashAppUpdateInfo1 cashapp): void |
| `countries` | `?(string[])` | Optional | The list of countries where a payment method is available. By default, all countries supported by the payment method. | getCountries(): ?array | setCountries(?array countries): void |
| `cup` | [`?GenericPmWithTdiUpdateInfo2`](../../doc/models/generic-pm-with-tdi-update-info-2.md) | Optional | Details to provide if `type` is **cup** (China Union Pay). | getCup(): ?GenericPmWithTdiUpdateInfo2 | setCup(?GenericPmWithTdiUpdateInfo2 cup): void |
| `currencies` | `?(string[])` | Optional | The list of currencies that a payment method supports. By default, all currencies supported by the payment method. | getCurrencies(): ?array | setCurrencies(?array currencies): void |
| `customRoutingFlags` | `?(string[])` | Optional | Custom routing flags for acquirer routing. | getCustomRoutingFlags(): ?array | setCustomRoutingFlags(?array customRoutingFlags): void |
| `diners` | [`?GenericPmWithTdiUpdateInfo3`](../../doc/models/generic-pm-with-tdi-update-info-3.md) | Optional | Details to provide if `type` is **diners**.<br>For merchants operating in Japan, Diners payments are processed through the JCB network. This means that you must include [JCB-specific fields](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/(merchantId)/paymentMethodSettings/(paymentMethodId)#request-jcb) in this object. | getDiners(): ?GenericPmWithTdiUpdateInfo3 | setDiners(?GenericPmWithTdiUpdateInfo3 diners): void |
| `discover` | [`?GenericPmWithTdiUpdateInfo4`](../../doc/models/generic-pm-with-tdi-update-info-4.md) | Optional | Details to provide if `type` is **discover**.<br>For merchants operating in Japan, request [Diners](https://docs.adyen.com/api-explorer/Management/latest/post/merchants/(merchantId)/paymentMethodSettings/(paymentMethodId)#request-diners) payment method instead. Discover is automatically requested, together with Diners. | getDiscover(): ?GenericPmWithTdiUpdateInfo4 | setDiscover(?GenericPmWithTdiUpdateInfo4 discover): void |
| `eftDirectdebitCA` | [`?GenericPmWithTdiUpdateInfo5`](../../doc/models/generic-pm-with-tdi-update-info-5.md) | Optional | Details to provide if `type` is **eft_directdebit_CA** (EFT PAD). | getEftDirectdebitCA(): ?GenericPmWithTdiUpdateInfo5 | setEftDirectdebitCA(?GenericPmWithTdiUpdateInfo5 eftDirectdebitCA): void |
| `eftposAustralia` | [`?GenericPmWithTdiUpdateInfo6`](../../doc/models/generic-pm-with-tdi-update-info-6.md) | Optional | Details to provide if `type` is **eftpos_australia**. | getEftposAustralia(): ?GenericPmWithTdiUpdateInfo6 | setEftposAustralia(?GenericPmWithTdiUpdateInfo6 eftposAustralia): void |
| `enabled` | `?bool` | Optional | Indicates whether the payment method is enabled (**true**) or disabled (**false**). | getEnabled(): ?bool | setEnabled(?bool enabled): void |
| `girocard` | [`?GenericPmWithTdiUpdateInfo7`](../../doc/models/generic-pm-with-tdi-update-info-7.md) | Optional | Details to provide if `type` is **girocard**. | getGirocard(): ?GenericPmWithTdiUpdateInfo7 | setGirocard(?GenericPmWithTdiUpdateInfo7 girocard): void |
| `ideal` | [`?GenericPmWithTdiUpdateInfo8`](../../doc/models/generic-pm-with-tdi-update-info-8.md) | Optional | Details to provide if `type` is **ideal**. | getIdeal(): ?GenericPmWithTdiUpdateInfo8 | setIdeal(?GenericPmWithTdiUpdateInfo8 ideal): void |
| `interacCard` | [`?GenericPmWithTdiUpdateInfo9`](../../doc/models/generic-pm-with-tdi-update-info-9.md) | Optional | Details to provide if `type` is **interac_card**. | getInteracCard(): ?GenericPmWithTdiUpdateInfo9 | setInteracCard(?GenericPmWithTdiUpdateInfo9 interacCard): void |
| `jcb` | [`?GenericPmWithTdiUpdateInfo10`](../../doc/models/generic-pm-with-tdi-update-info-10.md) | Optional | Details to provide if `type` is **jcb**.<br>For merchants operating in Japan, `midNumber`, `reuseMidNumber`, and `serviceLevel` fields are required.<br>For merchants operating outside of Japan, these fields are not required. | getJcb(): ?GenericPmWithTdiUpdateInfo10 | setJcb(?GenericPmWithTdiUpdateInfo10 jcb): void |
| `maestro` | [`?GenericPmWithTdiUpdateInfo11`](../../doc/models/generic-pm-with-tdi-update-info-11.md) | Optional | Details to provide if `type` is **maestro**.<br>In the US, `maestro` is not supported; use `maestro_usa` instead. | getMaestro(): ?GenericPmWithTdiUpdateInfo11 | setMaestro(?GenericPmWithTdiUpdateInfo11 maestro): void |
| `maestroUsa` | [`?GenericPmWithTdiUpdateInfo12`](../../doc/models/generic-pm-with-tdi-update-info-12.md) | Optional | Details to provide if `type` is **maestro_usa**.<br>Only for Maestro USA, otherwise use `maestro`. | getMaestroUsa(): ?GenericPmWithTdiUpdateInfo12 | setMaestroUsa(?GenericPmWithTdiUpdateInfo12 maestroUsa): void |
| `mc` | [`?GenericPmWithTdiUpdateInfo13`](../../doc/models/generic-pm-with-tdi-update-info-13.md) | Optional | Details to provide if `type` is **mc**. | getMc(): ?GenericPmWithTdiUpdateInfo13 | setMc(?GenericPmWithTdiUpdateInfo13 mc): void |
| `nyce` | [`?NyceUpdateInfo1`](../../doc/models/nyce-update-info-1.md) | Optional | Details to provide if `type` is **nyce**. | getNyce(): ?NyceUpdateInfo1 | setNyce(?NyceUpdateInfo1 nyce): void |
| `paybybankPlaid` | [`?PayByBankPlaidUpdateInfo1`](../../doc/models/pay-by-bank-plaid-update-info-1.md) | Optional | Details to provide if `type` is **paybybank_plaid**. | getPaybybankPlaid(): ?PayByBankPlaidUpdateInfo1 | setPaybybankPlaid(?PayByBankPlaidUpdateInfo1 paybybankPlaid): void |
| `pulse` | [`?PulseUpdateInfo1`](../../doc/models/pulse-update-info-1.md) | Optional | Details to provide if `type` is **pulse**. | getPulse(): ?PulseUpdateInfo1 | setPulse(?PulseUpdateInfo1 pulse): void |
| `sepadirectdebit` | [`?SepaDirectDebitUpdateInfo1`](../../doc/models/sepa-direct-debit-update-info-1.md) | Optional | Details to provide if `type` is **sepadirectdebit**. | getSepadirectdebit(): ?SepaDirectDebitUpdateInfo1 | setSepadirectdebit(?SepaDirectDebitUpdateInfo1 sepadirectdebit): void |
| `star` | [`?StarUpdateInfo1`](../../doc/models/star-update-info-1.md) | Optional | Details to provide if `type` is **star**. | getStar(): ?StarUpdateInfo1 | setStar(?StarUpdateInfo1 star): void |
| `storeId` | `?string` | Optional | The store for this payment method | getStoreId(): ?string | setStoreId(?string storeId): void |
| `storeIds` | `?(string[])` | Optional | The list of stores for this payment method | getStoreIds(): ?array | setStoreIds(?array storeIds): void |
| `visa` | [`?GenericPmWithTdiUpdateInfo14`](../../doc/models/generic-pm-with-tdi-update-info-14.md) | Optional | Details to provide if `type` is **visa**. | getVisa(): ?GenericPmWithTdiUpdateInfo14 | setVisa(?GenericPmWithTdiUpdateInfo14 visa): void |

## Example

```php
use AdyenLib\Models\Builders\UpdatePaymentMethodInfoBuilder;
use AdyenLib\Models\Builders\AccelUpdateInfo1Builder;
use AdyenLib\Models\Builders\TransactionDescriptionInfo1Builder;
use AdyenLib\Models\Type8Enum;
use AdyenLib\Models\Builders\AffirmUpdateInfo1Builder;
use AdyenLib\Models\Builders\BcmcUpdateInfo1Builder;
use AdyenLib\Models\Builders\GenericPmWithTdiUpdateInfo1Builder;
use AdyenLib\Models\Builders\CartesBancairesUpdateInfo1Builder;

$updatePaymentMethodInfo = UpdatePaymentMethodInfoBuilder::init()
    ->accel(
        AccelUpdateInfo1Builder::init()
            ->transactionDescription(
                TransactionDescriptionInfo1Builder::init()
                    ->doingBusinessAsName('doingBusinessAsName0')
                    ->type(Type8Enum::FIXED)
                    ->build()
            )
            ->build()
    )
    ->affirm(
        AffirmUpdateInfo1Builder::init()
            ->pricePlan('pricePlan8')
            ->build()
    )
    ->bcmc(
        BcmcUpdateInfo1Builder::init()
            ->transactionDescription(
                TransactionDescriptionInfo1Builder::init()
                    ->doingBusinessAsName('doingBusinessAsName0')
                    ->type(Type8Enum::FIXED)
                    ->build()
            )
            ->build()
    )
    ->carnet(
        GenericPmWithTdiUpdateInfo1Builder::init()
            ->transactionDescription(
                TransactionDescriptionInfo1Builder::init()
                    ->doingBusinessAsName('doingBusinessAsName0')
                    ->type(Type8Enum::FIXED)
                    ->build()
            )
            ->build()
    )
    ->cartesBancaires(
        CartesBancairesUpdateInfo1Builder::init()
            ->transactionDescription(
                TransactionDescriptionInfo1Builder::init()
                    ->doingBusinessAsName('doingBusinessAsName0')
                    ->type(Type8Enum::FIXED)
                    ->build()
            )
            ->build()
    )
    ->build();
```

