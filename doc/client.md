
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.TEST`** |
| timeout | `int` | Timeout for API calls in seconds.<br>*Default*: `30` |
| enableRetries | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| numberOfRetries | `int` | The number of retries to make.<br>*Default*: `0` |
| retryInterval | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| backOffFactor | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| maximumRetryWaitTime | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| httpStatusCodesToRetry | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524, 408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| httpMethodsToRetry | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT', 'GET', 'PUT'` |
| proxyConfiguration | [`ProxyConfigurationBuilder`](../doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |
| apiKeyAuthCredentials | [`ApiKeyAuthCredentials`](auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |
| basicAuthCredentials | [`BasicAuthCredentials`](auth/basic-authentication.md) | The Credentials Setter for Basic Authentication |
| clientKeyCredentials | [`ClientKeyCredentials`](auth/custom-query-parameter.md) | The Credentials Setter for Custom Query Parameter |

The API client can be initialized as follows:

```php
use AdyenLib\Environment;
use AdyenLib\Authentication\ApiKeyAuthCredentialsBuilder;
use AdyenLib\Authentication\BasicAuthCredentialsBuilder;
use AdyenLib\Authentication\ClientKeyCredentialsBuilder;
use AdyenLib\AdyenClientBuilder;

$client = AdyenClientBuilder::init()
    ->apiKeyAuthCredentials(
        ApiKeyAuthCredentialsBuilder::init(
            'X-API-Key'
        )
    )
    ->basicAuthCredentials(
        BasicAuthCredentialsBuilder::init(
            'Username',
            'Password'
        )
    )
    ->clientKeyCredentials(
        ClientKeyCredentialsBuilder::init(
            'clientKey'
        )
    )
    ->environment(Environment::TEST)
    ->build();
```

## Adyen Client

The gateway for the SDK. This class acts as a factory for the Apis and also holds the configuration of the SDK.

## Apis

| Name | Description |
|  --- | --- |
| getPaymentsApi() | Gets PaymentsApi |
| getDonationsApi() | Gets DonationsApi |
| getPaymentLinksApi() | Gets PaymentLinksApi |
| getModificationsApi() | Gets ModificationsApi |
| getRecurringApi() | Gets RecurringApi |
| getOrdersApi() | Gets OrdersApi |
| getUtilityApi() | Gets UtilityApi |
| getGeneralApi() | Gets GeneralApi |
| getInitializationApi() | Gets InitializationApi |
| getReviewingApi() | Gets ReviewingApi |
| getInstantPayoutsApi() | Gets InstantPayoutsApi |
| getRatesApi() | Gets RatesApi |
| getAccountCompanyLevelApi() | Gets AccountCompanyLevelApi |
| getAccountMerchantLevelApi() | Gets AccountMerchantLevelApi |
| getAccountStoreLevelApi() | Gets AccountStoreLevelApi |
| getPayoutSettingsMerchantLevelApi() | Gets PayoutSettingsMerchantLevelApi |
| getUsersCompanyLevelApi() | Gets UsersCompanyLevelApi |
| getUsersMerchantLevelApi() | Gets UsersMerchantLevelApi |
| getMyAPICredentialApi() | Gets MyAPICredentialApi |
| getAPICredentialsCompanyLevelApi() | Gets APICredentialsCompanyLevelApi |
| getAPICredentialsMerchantLevelApi() | Gets APICredentialsMerchantLevelApi |
| getAPIKeyCompanyLevelApi() | Gets APIKeyCompanyLevelApi |
| getAPIKeyMerchantLevelApi() | Gets APIKeyMerchantLevelApi |
| getClientKeyCompanyLevelApi() | Gets ClientKeyCompanyLevelApi |
| getClientKeyMerchantLevelApi() | Gets ClientKeyMerchantLevelApi |
| getAllowedOriginsCompanyLevelApi() | Gets AllowedOriginsCompanyLevelApi |
| getAllowedOriginsMerchantLevelApi() | Gets AllowedOriginsMerchantLevelApi |
| getWebhooksCompanyLevelApi() | Gets WebhooksCompanyLevelApi |
| getWebhooksMerchantLevelApi() | Gets WebhooksMerchantLevelApi |
| getPaymentMethodsMerchantLevelApi() | Gets PaymentMethodsMerchantLevelApi |
| getTerminalsTerminalLevelApi() | Gets TerminalsTerminalLevelApi |
| getTerminalActionsCompanyLevelApi() | Gets TerminalActionsCompanyLevelApi |
| getTerminalActionsTerminalLevelApi() | Gets TerminalActionsTerminalLevelApi |
| getTerminalOrdersCompanyLevelApi() | Gets TerminalOrdersCompanyLevelApi |
| getTerminalOrdersMerchantLevelApi() | Gets TerminalOrdersMerchantLevelApi |
| getTerminalSettingsCompanyLevelApi() | Gets TerminalSettingsCompanyLevelApi |
| getTerminalSettingsMerchantLevelApi() | Gets TerminalSettingsMerchantLevelApi |
| getTerminalSettingsStoreLevelApi() | Gets TerminalSettingsStoreLevelApi |
| getTerminalSettingsTerminalLevelApi() | Gets TerminalSettingsTerminalLevelApi |
| getAndroidFilesCompanyLevelApi() | Gets AndroidFilesCompanyLevelApi |
| getSplitConfigurationMerchantLevelApi() | Gets SplitConfigurationMerchantLevelApi |
| getDonationCampaignsApi() | Gets DonationCampaignsApi |
| getAccountHoldersApi() | Gets AccountHoldersApi |
| getAccountsApi() | Gets AccountsApi |
| getVerificationApi() | Gets VerificationApi |
| getBalancesOverviewApi() | Gets BalancesOverviewApi |
| getBalanceTransfersApi() | Gets BalanceTransfersApi |
| getPlatformApi() | Gets PlatformApi |
| getBalanceAccountsApi() | Gets BalanceAccountsApi |
| getBalancesApi() | Gets BalancesApi |
| getManagedPayoutSchedulesApi() | Gets ManagedPayoutSchedulesApi |
| getCustomPayoutSchedulesSweepsApi() | Gets CustomPayoutSchedulesSweepsApi |
| getAuthorizedCardUsersApi() | Gets AuthorizedCardUsersApi |
| getRecurringTopUpsApi() | Gets RecurringTopUpsApi |
| getPaymentInstrumentsApi() | Gets PaymentInstrumentsApi |
| getPaymentInstrumentGroupsApi() | Gets PaymentInstrumentGroupsApi |
| getTransactionRulesApi() | Gets TransactionRulesApi |
| getBankAccountValidationApi() | Gets BankAccountValidationApi |
| getNetworkTokensApi() | Gets NetworkTokensApi |
| getGrantAccountsApi() | Gets GrantAccountsApi |
| getGrantOffersApi() | Gets GrantOffersApi |
| getCardOrdersApi() | Gets CardOrdersApi |
| getDirectDebitMandatesApi() | Gets DirectDebitMandatesApi |
| getManageCardPINApi() | Gets ManageCardPINApi |
| getTransferRoutesApi() | Gets TransferRoutesApi |
| getSCADeviceManagementApi() | Gets SCADeviceManagementApi |
| getTransferLimitsBalanceAccountLevelApi() | Gets TransferLimitsBalanceAccountLevelApi |
| getTransferLimitsBalancePlatformLevelApi() | Gets TransferLimitsBalancePlatformLevelApi |
| getManageSCADevicesApi() | Gets ManageSCADevicesApi |
| getSCAAssociationManagementApi() | Gets SCAAssociationManagementApi |
| getTransfersApi() | Gets TransfersApi |
| getTransactionsApi() | Gets TransactionsApi |
| getCapitalApi() | Gets CapitalApi |
| getCashOutApi() | Gets CashOutApi |
| getDynamicOffersApi() | Gets DynamicOffersApi |
| getGrantsApi() | Gets GrantsApi |
| getSessionAuthenticationApi() | Gets SessionAuthenticationApi |
| getLegalEntitiesApi() | Gets LegalEntitiesApi |
| getTransferInstrumentsApi() | Gets TransferInstrumentsApi |
| getBusinessLinesApi() | Gets BusinessLinesApi |
| getDocumentsApi() | Gets DocumentsApi |
| getTermsOfServiceApi() | Gets TermsOfServiceApi |
| getPCIQuestionnairesApi() | Gets PCIQuestionnairesApi |
| getTaxEDeliveryConsentApi() | Gets TaxEDeliveryConsentApi |
| getHostedOnboardingApi() | Gets HostedOnboardingApi |
| getHostedOnboardingPageApi() | Gets HostedOnboardingPageApi |
| getPCIComplianceQuestionnairePageApi() | Gets PCIComplianceQuestionnairePageApi |
| getIDEALProfilesApi() | Gets IDEALProfilesApi |
| getAccountVerificationApi() | Gets AccountVerificationApi |
| getDisputeAttachmentsApi() | Gets DisputeAttachmentsApi |
| getRaiseDisputesApi() | Gets RaiseDisputesApi |
| getAPI() | Gets API |
| getPaymentsAppApi() | Gets PaymentsAppApi |

