
# Three DS 2 Request Fields

## Structure

`ThreeDS2RequestFields`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acctInfo` | [`?AcctInfo`](../../doc/models/acct-info.md) | Optional | Additional information about the cardholder’s account provided by the 3DS Requestor. | getAcctInfo(): ?AcctInfo | setAcctInfo(?AcctInfo acctInfo): void |
| `acctType` | [`?string(AcctTypeEnum)`](../../doc/models/acct-type-enum.md) | Optional | Indicates the type of account. For example, for a multi-account card product. Length: 2 characters. Allowed values:<br><br>* **01** — Not applicable<br>* **02** — Credit<br>* **03** — Debit<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getAcctType(): ?string | setAcctType(?string acctType): void |
| `acquirerBIN` | `?string` | Optional | Required for [authentication-only integration](https://docs.adyen.com/online-payments/3d-secure/other-3ds-flows/authentication-only). The acquiring BIN enrolled for 3D Secure 2. This string should match the value that you will use in the authorisation. Use 123456 on the Test platform. | getAcquirerBIN(): ?string | setAcquirerBIN(?string acquirerBIN): void |
| `acquirerMerchantID` | `?string` | Optional | Required for [authentication-only integration](https://docs.adyen.com/online-payments/3d-secure/other-3ds-flows/authentication-only). The merchantId that is enrolled for 3D Secure 2 by the merchant's acquirer. This string should match the value that you will use in the authorisation. Use 123456 on the Test platform. | getAcquirerMerchantID(): ?string | setAcquirerMerchantID(?string acquirerMerchantID): void |
| `addrMatch` | [`?string(AddrMatch1Enum)`](../../doc/models/addr-match-1-enum.md) | Optional | Indicates whether the cardholder shipping Address and cardholder billing address are the same. Allowed values:<br><br>* **Y** — Shipping Address matches Billing Address.<br>* **N** — Shipping Address does not match Billing Address.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `1` | getAddrMatch(): ?string | setAddrMatch(?string addrMatch): void |
| `authenticationOnly` | `?bool` | Optional | If set to true, you will only perform the [3D Secure 2 authentication](https://docs.adyen.com/online-payments/3d-secure/other-3ds-flows/authentication-only), and not the payment authorisation.<br><br>**Default**: `false` | getAuthenticationOnly(): ?bool | setAuthenticationOnly(?bool authenticationOnly): void |
| `challengeIndicator` | [`?string(ChallengeIndicatorEnum)`](../../doc/models/challenge-indicator-enum.md) | Optional | Possibility to specify a preference for receiving a challenge from the issuer.<br>Allowed values:<br><br>* `noPreference`<br>* `requestNoChallenge`<br>* `requestChallenge`<br>* `requestChallengeAsMandate` | getChallengeIndicator(): ?string | setChallengeIndicator(?string challengeIndicator): void |
| `deviceRenderOptions` | [`?DeviceRenderOptions`](../../doc/models/device-render-options.md) | Optional | Display options for the 3D Secure 2 SDK.<br>Optional and only for `deviceChannel` **app**. | getDeviceRenderOptions(): ?DeviceRenderOptions | setDeviceRenderOptions(?DeviceRenderOptions deviceRenderOptions): void |
| `homePhone` | [`?Phone3`](../../doc/models/phone-3.md) | Optional | The home phone number provided by the cardholder. The phone number must consist of a country code, followed by the number. If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`, and did not send the shopper's phone number in `telephoneNumber`. | getHomePhone(): ?Phone3 | setHomePhone(?Phone3 homePhone): void |
| `mcc` | `?string` | Optional | Required for merchants that have been enrolled for 3D Secure 2 by another party than Adyen, mostly [authentication-only integrations](https://docs.adyen.com/online-payments/3d-secure/other-3ds-flows/authentication-only). The `mcc` is a four-digit code with which the previously given `acquirerMerchantID` is registered at the scheme. | getMcc(): ?string | setMcc(?string mcc): void |
| `merchantName` | `?string` | Optional | Required for [authentication-only integration](https://docs.adyen.com/online-payments/3d-secure/other-3ds-flows/authentication-only). The merchant name that the issuer presents to the shopper if they get a challenge. We recommend to use the same value that you will use in the authorization. Maximum length is 40 characters.<br><br>> Optional for a [full 3D Secure 2 integration](https://docs.adyen.com/online-payments/3d-secure/native-3ds2/api-integration). Use this field if you are enrolled for 3D Secure 2 with us and want to override the merchant name already configured on your account. | getMerchantName(): ?string | setMerchantName(?string merchantName): void |
| `messageVersion` | `?string` | Optional | The `messageVersion` value indicating the 3D Secure 2 protocol version. | getMessageVersion(): ?string | setMessageVersion(?string messageVersion): void |
| `mobilePhone` | [`?Phone1`](../../doc/models/phone-1.md) | Optional | The mobile phone number provided by the cardholder. The phone number must consist of a country code, followed by the number. If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`, and did not send the shopper's phone number in `telephoneNumber`. | getMobilePhone(): ?Phone1 | setMobilePhone(?Phone1 mobilePhone): void |
| `notificationURL` | `?string` | Optional | URL to where the issuer should send the `CRes`. Required if you are not using components for `channel` **Web** or if you are using classic integration `deviceChannel` **browser**. | getNotificationURL(): ?string | setNotificationURL(?string notificationURL): void |
| `payTokenInd` | `?bool` | Optional | Value **true** indicates that the transaction was de-tokenised prior to being received by the ACS. | getPayTokenInd(): ?bool | setPayTokenInd(?bool payTokenInd): void |
| `paymentAuthenticationUseCase` | `?string` | Optional | Indicates the type of payment for which an authentication is requested (message extension) | getPaymentAuthenticationUseCase(): ?string | setPaymentAuthenticationUseCase(?string paymentAuthenticationUseCase): void |
| `purchaseInstalData` | `?string` | Optional | Indicates the maximum number of authorisations permitted for instalment payments. Length: 1–3 characters.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `3` | getPurchaseInstalData(): ?string | setPurchaseInstalData(?string purchaseInstalData): void |
| `recurringExpiry` | `?string` | Optional | Date after which no further authorisations shall be performed. Format: YYYYMMDD | getRecurringExpiry(): ?string | setRecurringExpiry(?string recurringExpiry): void |
| `recurringFrequency` | `?string` | Optional | Indicates the minimum number of days between authorisations. Maximum length: 4 characters.<br><br>**Constraints**: *Maximum Length*: `4` | getRecurringFrequency(): ?string | setRecurringFrequency(?string recurringFrequency): void |
| `sdkAppID` | `?string` | Optional | The `sdkAppID` value as received from the 3D Secure 2 SDK. | getSdkAppID(): ?string | setSdkAppID(?string sdkAppID): void |
| `sdkEphemPubKey` | [`?SDKEphemPubKey1`](../../doc/models/sdk-ephem-pub-key-1.md) | Optional | The `sdkEphemPubKey` value as received from the 3D Secure 2 SDK. | getSdkEphemPubKey(): ?SDKEphemPubKey1 | setSdkEphemPubKey(?SDKEphemPubKey1 sdkEphemPubKey): void |
| `sdkMaxTimeout` | `?int` | Optional | The maximum amount of time in minutes for the 3D Secure 2 authentication process.<br>Optional and only for `deviceChannel` set to **app**. Defaults to **60** minutes.<br><br>**Default**: `60` | getSdkMaxTimeout(): ?int | setSdkMaxTimeout(?int sdkMaxTimeout): void |
| `sdkReferenceNumber` | `?string` | Optional | The `sdkReferenceNumber` value as received from the 3D Secure 2 SDK. | getSdkReferenceNumber(): ?string | setSdkReferenceNumber(?string sdkReferenceNumber): void |
| `sdkTransID` | `?string` | Optional | The `sdkTransID` value as received from the 3D Secure 2 SDK. | getSdkTransID(): ?string | setSdkTransID(?string sdkTransID): void |
| `threeDSCompInd` | `?string` | Optional | Completion indicator for the device fingerprinting. | getThreeDSCompInd(): ?string | setThreeDSCompInd(?string threeDSCompInd): void |
| `threeDSRequestorAuthenticationInd` | `?string` | Optional | Indicates the type of Authentication request. | getThreeDSRequestorAuthenticationInd(): ?string | setThreeDSRequestorAuthenticationInd(?string threeDSRequestorAuthenticationInd): void |
| `threeDSRequestorAuthenticationInfo` | [`?ThreeDSRequestorAuthenticationInfo`](../../doc/models/three-ds-requestor-authentication-info.md) | Optional | Information about how the 3DS Requestor authenticated the cardholder before or during the transaction | getThreeDSRequestorAuthenticationInfo(): ?ThreeDSRequestorAuthenticationInfo | setThreeDSRequestorAuthenticationInfo(?ThreeDSRequestorAuthenticationInfo threeDSRequestorAuthenticationInfo): void |
| `threeDSRequestorChallengeInd` | [`?string(ThreeDSRequestorChallengeIndEnum)`](../../doc/models/three-ds-requestor-challenge-ind-enum.md) | Optional | Indicates whether a challenge is requested for this transaction. Possible values:<br><br>* **01** — No preference<br>* **02** — No challenge requested<br>* **03** — Challenge requested (3DS Requestor preference)<br>* **04** — Challenge requested (Mandate)<br>* **05** — No challenge (transactional risk analysis is already performed)<br>* **06** — Data Only | getThreeDSRequestorChallengeInd(): ?string | setThreeDSRequestorChallengeInd(?string threeDSRequestorChallengeInd): void |
| `threeDSRequestorID` | `?string` | Optional | Required for [authentication-only integration](https://docs.adyen.com/online-payments/3d-secure/other-3ds-flows/authentication-only) for Visa. Unique 3D Secure requestor identifier assigned by the Directory Server when you enrol for 3D Secure 2. | getThreeDSRequestorID(): ?string | setThreeDSRequestorID(?string threeDSRequestorID): void |
| `threeDSRequestorName` | `?string` | Optional | Required for [authentication-only integration](https://docs.adyen.com/online-payments/3d-secure/other-3ds-flows/authentication-only) for Visa. Unique 3D Secure requestor name assigned by the Directory Server when you enrol for 3D Secure 2. | getThreeDSRequestorName(): ?string | setThreeDSRequestorName(?string threeDSRequestorName): void |
| `threeDSRequestorPriorAuthenticationInfo` | [`?ThreeDSRequestorPriorAuthenticationInfo`](../../doc/models/three-ds-requestor-prior-authentication-info.md) | Optional | Information about how the 3DS Requestor authenticated the cardholder as part of a previous 3DS transaction. | getThreeDSRequestorPriorAuthenticationInfo(): ?ThreeDSRequestorPriorAuthenticationInfo | setThreeDSRequestorPriorAuthenticationInfo(?ThreeDSRequestorPriorAuthenticationInfo threeDSRequestorPriorAuthenticationInfo): void |
| `threeDSRequestorURL` | `?string` | Optional | URL of the (customer service) website that will be shown to the shopper in case of technical errors during the 3D Secure 2 process. | getThreeDSRequestorURL(): ?string | setThreeDSRequestorURL(?string threeDSRequestorURL): void |
| `transType` | [`?string(TransTypeEnum)`](../../doc/models/trans-type-enum.md) | Optional | Identifies the type of transaction being authenticated. Length: 2 characters. Allowed values:<br><br>* **01** — Goods/Service Purchase<br>* **03** — Check Acceptance<br>* **10** — Account Funding<br>* **11** — Quasi-Cash Transaction<br>* **28** — Prepaid Activation and Load<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getTransType(): ?string | setTransType(?string transType): void |
| `transactionType` | [`?string(TransactionTypeEnum)`](../../doc/models/transaction-type-enum.md) | Optional | Identify the type of the transaction being authenticated. | getTransactionType(): ?string | setTransactionType(?string transactionType): void |
| `whiteListStatus` | `?string` | Optional | The `whiteListStatus` value returned from a previous 3D Secure 2 transaction, only applicable for 3D Secure 2 protocol version 2.2.0. | getWhiteListStatus(): ?string | setWhiteListStatus(?string whiteListStatus): void |
| `workPhone` | [`?Phone2`](../../doc/models/phone-2.md) | Optional | The work phone number provided by the cardholder. The phone number must consist of a country code, followed by the number. If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`, and did not send the shopper's phone number in `telephoneNumber`. | getWorkPhone(): ?Phone2 | setWorkPhone(?Phone2 workPhone): void |

## Example

```php
use AdyenLib\Models\Builders\ThreeDS2RequestFieldsBuilder;
use AdyenLib\Models\Builders\AcctInfoBuilder;
use AdyenLib\Models\ChAccAgeIndEnum;
use AdyenLib\Models\ChAccChangeIndEnum;
use AdyenLib\Models\ChAccPwChangeIndEnum;
use AdyenLib\Models\AcctTypeEnum;
use AdyenLib\Models\AddrMatch1Enum;

$threeDS2RequestFields = ThreeDS2RequestFieldsBuilder::init()
    ->acctInfo(
        AcctInfoBuilder::init()
            ->chAccAgeInd(ChAccAgeIndEnum::ENUM_05)
            ->chAccChange('chAccChange8')
            ->chAccChangeInd(ChAccChangeIndEnum::ENUM_01)
            ->chAccPwChange('chAccPwChange8')
            ->chAccPwChangeInd(ChAccPwChangeIndEnum::ENUM_03)
            ->build()
    )
    ->acctType(AcctTypeEnum::ENUM_02)
    ->acquirerBIN('acquirerBIN6')
    ->acquirerMerchantID('acquirerMerchantID4')
    ->addrMatch(AddrMatch1Enum::Y)
    ->authenticationOnly(false)
    ->sdkMaxTimeout(60)
    ->build();
```

