
# Payment Request Payment Method

## Data Type

`ACHDirectDebit|Affirm|Afterpay|Alma|AmazonPay|ANCV|AndroidPay|ApplePayDetails|AuPay|BACSDirectDebit|BillDesk|BLIK|CardDetails|StoredPaymentMethod|Cellulant|DBarai|DirectDebitAu|Doku|Dragonpay|EBankingFinland|Voucher|EFTDirectDebit|DetailsOfTokensThatAreNotStoredWithAdyen|Fastlane|StoredPaymentMethod2|GooglePayDetails|IdealDetails|Klarna|KlarnaNetwork|Masterpass|MBWay|MobilePay|MOLPay|OpenInvoice|PayByBankAISDirectDebit|PayByBank|PayPal|PayPay|PayTo|PayU|PayWithGoogleDetails|PaymentDetails|StoredPaymentMethod4|StoredPaymentMethod5|PSELatam|RakutenPay|Ratepay|Riverty|SamsungPay|SEPADirectDebit|StoredPaymentMethod6|Twint|UPICollect|UPIIntent|UPIQR|Vipps|VisaCheckout|WeChatPay|WeChatPayMiniProgram|Zip`

## Cases

| Type |
|  --- |
| [`ACHDirectDebit`](../../../doc/models/ach-direct-debit.md) |
| [`Affirm`](../../../doc/models/affirm.md) |
| [`Afterpay`](../../../doc/models/afterpay.md) |
| [`Alma`](../../../doc/models/alma.md) |
| [`AmazonPay`](../../../doc/models/amazon-pay.md) |
| [`ANCV`](../../../doc/models/ancv.md) |
| [`AndroidPay`](../../../doc/models/android-pay.md) |
| [`ApplePayDetails`](../../../doc/models/apple-pay-details.md) |
| [`AuPay`](../../../doc/models/au-pay.md) |
| [`BACSDirectDebit`](../../../doc/models/bacs-direct-debit.md) |
| [`BillDesk`](../../../doc/models/bill-desk.md) |
| [`BLIK`](../../../doc/models/blik.md) |
| [`CardDetails`](../../../doc/models/card-details.md) |
| [`StoredPaymentMethod`](../../../doc/models/stored-payment-method.md) |
| [`Cellulant`](../../../doc/models/cellulant.md) |
| [`DBarai`](../../../doc/models/d-barai.md) |
| [`DirectDebitAu`](../../../doc/models/direct-debit-au.md) |
| [`Doku`](../../../doc/models/doku.md) |
| [`Dragonpay`](../../../doc/models/dragonpay.md) |
| [`EBankingFinland`](../../../doc/models/e-banking-finland.md) |
| [`Voucher`](../../../doc/models/voucher.md) |
| [`EFTDirectDebit`](../../../doc/models/eft-direct-debit.md) |
| [`DetailsOfTokensThatAreNotStoredWithAdyen`](../../../doc/models/details-of-tokens-that-are-not-stored-with-adyen.md) |
| [`Fastlane`](../../../doc/models/fastlane.md) |
| [`StoredPaymentMethod2`](../../../doc/models/stored-payment-method-2.md) |
| [`GooglePayDetails`](../../../doc/models/google-pay-details.md) |
| [`IdealDetails`](../../../doc/models/ideal-details.md) |
| [`Klarna`](../../../doc/models/klarna.md) |
| [`KlarnaNetwork`](../../../doc/models/klarna-network.md) |
| [`Masterpass`](../../../doc/models/masterpass.md) |
| [`MBWay`](../../../doc/models/mb-way.md) |
| [`MobilePay`](../../../doc/models/mobile-pay.md) |
| [`MOLPay`](../../../doc/models/mol-pay.md) |
| [`OpenInvoice`](../../../doc/models/open-invoice.md) |
| [`PayByBankAISDirectDebit`](../../../doc/models/pay-by-bank-ais-direct-debit.md) |
| [`PayByBank`](../../../doc/models/pay-by-bank.md) |
| [`PayPal`](../../../doc/models/pay-pal.md) |
| [`PayPay`](../../../doc/models/pay-pay.md) |
| [`PayTo`](../../../doc/models/pay-to.md) |
| [`PayU`](../../../doc/models/pay-u.md) |
| [`PayWithGoogleDetails`](../../../doc/models/pay-with-google-details.md) |
| [`PaymentDetails`](../../../doc/models/payment-details.md) |
| [`StoredPaymentMethod4`](../../../doc/models/stored-payment-method-4.md) |
| [`StoredPaymentMethod5`](../../../doc/models/stored-payment-method-5.md) |
| [`PSELatam`](../../../doc/models/pse-latam.md) |
| [`RakutenPay`](../../../doc/models/rakuten-pay.md) |
| [`Ratepay`](../../../doc/models/ratepay.md) |
| [`Riverty`](../../../doc/models/riverty.md) |
| [`SamsungPay`](../../../doc/models/samsung-pay.md) |
| [`SEPADirectDebit`](../../../doc/models/sepa-direct-debit.md) |
| [`StoredPaymentMethod6`](../../../doc/models/stored-payment-method-6.md) |
| [`Twint`](../../../doc/models/twint.md) |
| [`UPICollect`](../../../doc/models/upi-collect.md) |
| [`UPIIntent`](../../../doc/models/upi-intent.md) |
| [`UPIQR`](../../../doc/models/upiqr.md) |
| [`Vipps`](../../../doc/models/vipps.md) |
| [`VisaCheckout`](../../../doc/models/visa-checkout.md) |
| [`WeChatPay`](../../../doc/models/we-chat-pay.md) |
| [`WeChatPayMiniProgram`](../../../doc/models/we-chat-pay-mini-program.md) |
| [`Zip`](../../../doc/models/zip.md) |

## ACHDirectDebit

### Initialization Code

#### Example

```php
$value = ACHDirectDebitBuilder::init()
    ->type(TypeEnum::ACH)
    ->build();
```

## Affirm

### Initialization Code

#### Example

```php
$value = AffirmBuilder::init()
    ->type(Type1Enum::AFFIRM)
    ->build();
```

## Afterpay

### Initialization Code

#### Example

```php
$value = AfterpayBuilder::init(
    Type2Enum::AFTERPAY_DEFAULT
)->build();
```

## Alma

### Initialization Code

#### Example

```php
$value = AlmaBuilder::init()->build();
```

## AmazonPay

### Initialization Code

#### Example

```php
$value = AmazonPayBuilder::init()
    ->type(Type4Enum::AMAZONPAY)
    ->build();
```

## ANCV

### Initialization Code

#### Example

```php
$value = ANCVBuilder::init()->build();
```

## AndroidPay

### Initialization Code

#### Example

```php
$value = AndroidPayBuilder::init()
    ->type(Type6Enum::ANDROIDPAY)
    ->build();
```

## ApplePayDetails

### Initialization Code

#### Example

```php
$value = ApplePayDetailsBuilder::init(
    'applePayToken0'
)
    ->type(Type7Enum::APPLEPAY)
    ->build();
```

## AuPay

### Initialization Code

#### Example

```php
$value = AuPayBuilder::init()
    ->type(Type9Enum::AUPAY)
    ->build();
```

## BACSDirectDebit

### Initialization Code

#### Example

```php
$value = BACSDirectDebitBuilder::init()
    ->type(Type10Enum::DIRECTDEBIT_GB)
    ->build();
```

## BillDesk

### Initialization Code

#### Example

```php
$value = BillDeskBuilder::init(
    'issuer0',
    Type12Enum::BILLDESK_ONLINE
)->build();
```

## BLIK

### Initialization Code

#### Example

```php
$value = BLIKBuilder::init()->build();
```

## CardDetails

### Initialization Code

#### Example

```php
$value = CardDetailsBuilder::init()
    ->type(Type14Enum::SCHEME)
    ->build();
```

## StoredPaymentMethod

### Initialization Code

#### Example

```php
$value = StoredPaymentMethodBuilder::init()
    ->type(Type16Enum::CASHAPP)
    ->build();
```

## Cellulant

### Initialization Code

#### Example

```php
$value = CellulantBuilder::init()
    ->type(Type17Enum::CELLULANT)
    ->build();
```

## DBarai

### Initialization Code

#### Example

```php
$value = DBaraiBuilder::init()
    ->type(Type20Enum::DBARAI)
    ->build();
```

## DirectDebitAu

### Initialization Code

#### Example

```php
$value = DirectDebitAuBuilder::init(
    'holderName0'
)
    ->type(Type22Enum::DIRECTDEBIT_AU)
    ->build();
```

## Doku

### Initialization Code

#### Example

```php
$value = DokuBuilder::init(
    'firstName6',
    'lastName2',
    'shopperEmail8',
    Type23Enum::DOKU_BNI_VA
)->build();
```

## Dragonpay

### Initialization Code

#### Example

```php
$value = DragonpayBuilder::init(
    'issuer2',
    Type28Enum::DRAGONPAY_OTC_NON_BANKING
)->build();
```

## EBankingFinland

### Initialization Code

#### Example

```php
$value = EBankingFinlandBuilder::init()->build();
```

## Voucher

### Initialization Code

#### Example

```php
$value = VoucherBuilder::init(
    'firstName6',
    'lastName2',
    'shopperEmail2',
    'telephoneNumber0',
    Type29Enum::ECONTEXT_STORES
)->build();
```

## EFTDirectDebit

### Initialization Code

#### Example

```php
$value = EFTDirectDebitBuilder::init()
    ->type(Type30Enum::EFT_DIRECTDEBIT_CA)
    ->build();
```

## DetailsOfTokensThatAreNotStoredWithAdyen

### Initialization Code

#### Example

```php
$value = DetailsOfTokensThatAreNotStoredWithAdyenBuilder::init(
    'storedPaymentMethodId8'
)->build();
```

## Fastlane

### Initialization Code

#### Example

```php
$value = FastlaneBuilder::init(
    'fastlaneData2'
)->build();
```

## StoredPaymentMethod2

### Initialization Code

#### Example

```php
$value = StoredPaymentMethod2Builder::init(
    'issuer4',
    Type31Enum::EPS
)->build();
```

## GooglePayDetails

### Initialization Code

#### Example

```php
$value = GooglePayDetailsBuilder::init(
    'googlePayToken8'
)
    ->type(Type24Enum::GOOGLEPAY)
    ->build();
```

## IdealDetails

### Initialization Code

#### Example

```php
$value = IdealDetailsBuilder::init()
    ->type(Type25Enum::IDEAL)
    ->build();
```

## Klarna

### Initialization Code

#### Example

```php
$value = KlarnaBuilder::init(
    Type34Enum::KLARNA
)->build();
```

## KlarnaNetwork

### Initialization Code

#### Example

```php
$value = KlarnaNetworkBuilder::init()->build();
```

## Masterpass

### Initialization Code

#### Example

```php
$value = MasterpassBuilder::init(
    'masterpassTransactionId0'
)
    ->type(Type35Enum::MASTERPASS)
    ->build();
```

## MBWay

### Initialization Code

#### Example

```php
$value = MBWayBuilder::init(
    'shopperEmail4',
    'telephoneNumber4'
)
    ->type(Type36Enum::MBWAY)
    ->build();
```

## MobilePay

### Initialization Code

#### Example

```php
$value = MobilePayBuilder::init()
    ->type(Type37Enum::MOBILEPAY)
    ->build();
```

## MOLPay

### Initialization Code

#### Example

```php
$value = MOLPayBuilder::init(
    'issuer0',
    Type38Enum::MOLPAY_EBANKING_FPX_MY
)->build();
```

## OpenInvoice

### Initialization Code

#### Example

```php
$value = OpenInvoiceBuilder::init()
    ->type(Type39Enum::OPENINVOICE)
    ->build();
```

## PayByBankAISDirectDebit

### Initialization Code

#### Example

```php
$value = PayByBankAISDirectDebitBuilder::init()->build();
```

## PayByBank

### Initialization Code

#### Example

```php
$value = PayByBankBuilder::init()->build();
```

## PayPal

### Initialization Code

#### Example

```php
$value = PayPalBuilder::init()->build();
```

## PayPay

### Initialization Code

#### Example

```php
$value = PayPayBuilder::init()
    ->type(Type40Enum::PAYPAY)
    ->build();
```

## PayTo

### Initialization Code

#### Example

```php
$value = PayToBuilder::init()
    ->type(Type41Enum::PAYTO)
    ->build();
```

## PayU

### Initialization Code

#### Example

```php
$value = PayUBuilder::init()->build();
```

## PayWithGoogleDetails

### Initialization Code

#### Example

```php
$value = PayWithGoogleDetailsBuilder::init(
    'googlePayToken0'
)
    ->type(Type26Enum::PAYWITHGOOGLE)
    ->build();
```

## PaymentDetails

### Initialization Code

#### Example

```php
$value = PaymentDetailsBuilder::init()->build();
```

## StoredPaymentMethod4

### Initialization Code

#### Example

```php
$value = StoredPaymentMethod4Builder::init()->build();
```

## StoredPaymentMethod5

### Initialization Code

#### Example

```php
$value = StoredPaymentMethod5Builder::init()
    ->type(Type45Enum::PAYBYBANK_PIX)
    ->build();
```

## PSELatam

### Initialization Code

#### Example

```php
$value = PSELatamBuilder::init(
    'bank4',
    'clientType4',
    'identification4',
    'identificationType8'
)->build();
```

## RakutenPay

### Initialization Code

#### Example

```php
$value = RakutenPayBuilder::init()
    ->type(Type47Enum::RAKUTENPAY)
    ->build();
```

## Ratepay

### Initialization Code

#### Example

```php
$value = RatepayBuilder::init(
    Type48Enum::RATEPAY
)->build();
```

## Riverty

### Initialization Code

#### Example

```php
$value = RivertyBuilder::init(
    Type49Enum::RIVERTY
)->build();
```

## SamsungPay

### Initialization Code

#### Example

```php
$value = SamsungPayBuilder::init(
    'samsungPayToken6'
)
    ->type(Type50Enum::SAMSUNGPAY)
    ->build();
```

## SEPADirectDebit

### Initialization Code

#### Example

```php
$value = SEPADirectDebitBuilder::init(
    'iban4',
    'ownerName4'
)
    ->type(Type51Enum::SEPADIRECTDEBIT)
    ->build();
```

## StoredPaymentMethod6

### Initialization Code

#### Example

```php
$value = StoredPaymentMethod6Builder::init()->build();
```

## Twint

### Initialization Code

#### Example

```php
$value = TwintBuilder::init()->build();
```

## UPICollect

### Initialization Code

#### Example

```php
$value = UPICollectBuilder::init()->build();
```

## UPIIntent

### Initialization Code

#### Example

```php
$value = UPIIntentBuilder::init()->build();
```

## UPIQR

### Initialization Code

#### Example

```php
$value = UPIQRBuilder::init()->build();
```

## Vipps

### Initialization Code

#### Example

```php
$value = VippsBuilder::init(
    'telephoneNumber0'
)
    ->type(Type54Enum::VIPPS)
    ->build();
```

## VisaCheckout

### Initialization Code

#### Example

```php
$value = VisaCheckoutBuilder::init(
    'visaCheckoutCallId0'
)
    ->type(Type55Enum::VISACHECKOUT)
    ->build();
```

## WeChatPay

### Initialization Code

#### Example

```php
$value = WeChatPayBuilder::init()
    ->type(Type56Enum::WECHATPAY)
    ->build();
```

## WeChatPayMiniProgram

### Initialization Code

#### Example

```php
$value = WeChatPayMiniProgramBuilder::init()
    ->type(Type57Enum::WECHATPAYMINIPROGRAM)
    ->build();
```

## Zip

### Initialization Code

#### Example

```php
$value = ZipBuilder::init()
    ->type(Type58Enum::ZIP)
    ->build();
```

