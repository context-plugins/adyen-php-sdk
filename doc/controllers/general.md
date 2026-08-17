# General

```php
$generalApi = $client->getGeneralApi();
```

## Class Name

`GeneralApi`

## Methods

* [Post-Create Permit](../../doc/controllers/general.md#post-create-permit)
* [Post-Disable](../../doc/controllers/general.md#post-disable)
* [Post-Disable Permit](../../doc/controllers/general.md#post-disable-permit)
* [Post-List Recurring Details](../../doc/controllers/general.md#post-list-recurring-details)
* [Post-Notify Shopper](../../doc/controllers/general.md#post-notify-shopper)
* [Post-Schedule Account Updater](../../doc/controllers/general.md#post-schedule-account-updater)
* [Post-Get 3 Ds Availability](../../doc/controllers/general.md#post-get-3-ds-availability)
* [Post-Get Cost Estimate](../../doc/controllers/general.md#post-get-cost-estimate)
* [Post-Change Status](../../doc/controllers/general.md#post-change-status)
* [Post-Check Balance](../../doc/controllers/general.md#post-check-balance)
* [Post-Issue](../../doc/controllers/general.md#post-issue)
* [Post-Load](../../doc/controllers/general.md#post-load)
* [Post-Merge Balance](../../doc/controllers/general.md#post-merge-balance)
* [Post-Void Transaction](../../doc/controllers/general.md#post-void-transaction)
* [Post-Request Subject Erasure](../../doc/controllers/general.md#post-request-subject-erasure)
* [Post-Create Test Card Ranges](../../doc/controllers/general.md#post-create-test-card-ranges)
* [Post-Create Notification Configuration](../../doc/controllers/general.md#post-create-notification-configuration)
* [Post-Delete Notification Configurations](../../doc/controllers/general.md#post-delete-notification-configurations)
* [Post-Get Notification Configuration](../../doc/controllers/general.md#post-get-notification-configuration)
* [Post-Get Notification Configuration List](../../doc/controllers/general.md#post-get-notification-configuration-list)
* [Post-Test Notification Configuration](../../doc/controllers/general.md#post-test-notification-configuration)
* [Post-Update Notification Configuration](../../doc/controllers/general.md#post-update-notification-configuration)
* [Post-Account Holder Balance](../../doc/controllers/general.md#post-account-holder-balance)
* [Post-Account Holder Transaction List](../../doc/controllers/general.md#post-account-holder-transaction-list)
* [Post-Debit Account Holder](../../doc/controllers/general.md#post-debit-account-holder)
* [Post-Payout Account Holder](../../doc/controllers/general.md#post-payout-account-holder)
* [Post-Refund Funds Transfer](../../doc/controllers/general.md#post-refund-funds-transfer)
* [Post-Refund Not Paid Out Transfers](../../doc/controllers/general.md#post-refund-not-paid-out-transfers)
* [Post-Setup Beneficiary](../../doc/controllers/general.md#post-setup-beneficiary)
* [Post-Transfer Funds](../../doc/controllers/general.md#post-transfer-funds)
* [Post-Accept Dispute](../../doc/controllers/general.md#post-accept-dispute)
* [Post-Defend Dispute](../../doc/controllers/general.md#post-defend-dispute)
* [Post-Delete Dispute Defense Document](../../doc/controllers/general.md#post-delete-dispute-defense-document)
* [Post-Retrieve Applicable Defense Reasons](../../doc/controllers/general.md#post-retrieve-applicable-defense-reasons)
* [Post-Supply Defense Document](../../doc/controllers/general.md#post-supply-defense-document)
* [Post-Sessions](../../doc/controllers/general.md#post-sessions)
* [Post-Assign Terminals](../../doc/controllers/general.md#post-assign-terminals)
* [Post-Find Terminal](../../doc/controllers/general.md#post-find-terminal)
* [Post-Get Stores Under Account](../../doc/controllers/general.md#post-get-stores-under-account)
* [Post-Get Terminal Details](../../doc/controllers/general.md#post-get-terminal-details)
* [Post-Get Terminals Under Account](../../doc/controllers/general.md#post-get-terminals-under-account)


# Post-Create Permit

**This endpoint is deprecated.**

Create permits for a recurring contract, including support for defining restrictions.

```php
function postCreatePermit(?CreatePermitRequest $body = null): CreatePermitResult
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CreatePermitRequest`](../../doc/models/create-permit-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CreatePermitResult`](../../doc/models/create-permit-result.md)

## Example Usage

```php
$body = CreatePermitRequestBuilder::init(
    'merchantAccount2',
    [
        PermitBuilder::init()->build()
    ],
    'recurringDetailReference6',
    'shopperReference4'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postCreatePermit($body);
    echo 'CreatePermitResult:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Disable

Disables stored payment details to stop charging a shopper with this particular recurring detail ID.

For more information, refer to [Disable stored details](https://docs.adyen.com/online-payments/classic-integrations/classic-api-integration/tokenization/disable-stored-details).

```php
function postDisable(?DisableRequest $body = null): DisableResult
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DisableRequest`](../../doc/models/disable-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`DisableResult`](../../doc/models/disable-result.md)

## Example Usage

```php
$body = DisableRequestBuilder::init(
    'YOUR_MERCHANT_ACCOUNT',
    'YOUR_SHOPPER_REFERENCE'
)
    ->recurringDetailReference('8314442372419167')
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postDisable($body);
    echo 'DisableResult:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Disable Permit

**This endpoint is deprecated.**

Disable a permit that was previously linked to a recurringDetailReference.

```php
function postDisablePermit(?DisablePermitRequest $body = null): DisablePermitResult
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DisablePermitRequest`](../../doc/models/disable-permit-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`DisablePermitResult`](../../doc/models/disable-permit-result.md)

## Example Usage

```php
$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postDisablePermit();
    echo 'DisablePermitResult:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-List Recurring Details

Lists the stored payment details for a shopper, if there are any available. The recurring detail ID can be used with a regular authorisation request to charge the shopper. A summary of the payment detail is returned for presentation to the shopper.

For more information, refer to [Retrieve stored details](https://docs.adyen.com/classic-integration/recurring-payments/retrieve-stored-details/).

```php
function postListRecurringDetails(?RecurringDetailsRequest $body = null): RecurringDetailsResult
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?RecurringDetailsRequest`](../../doc/models/recurring-details-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`RecurringDetailsResult`](../../doc/models/recurring-details-result.md)

## Example Usage

```php
$body = RecurringDetailsRequestBuilder::init(
    'YOUR_MERCHANT_ACCOUNT',
    'YOUR_SHOPPER_REFERENCE'
)
    ->recurring(
        RecurringBuilder::init()
            ->contract(ContractEnum::RECURRING)
            ->build()
    )
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postListRecurringDetails($body);
    echo 'RecurringDetailsResult:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Notify Shopper

Sends a request to the issuer so they can inform the shopper about the upcoming recurring payment. This endpoint is used only for local acquiring in India. For more information, refer to [Recurring card payments in India](https://docs.adyen.com/payment-methods/cards/cards-recurring-india).

```php
function postNotifyShopper(?NotifyShopperRequest $body = null): NotifyShopperResult
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?NotifyShopperRequest`](../../doc/models/notify-shopper-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`NotifyShopperResult`](../../doc/models/notify-shopper-result.md)

## Example Usage

```php
$body = NotifyShopperRequestBuilder::init(
    AmountBuilder::init(
        'INR',
        1000
    )->build(),
    'YOUR_MERCHANT_ACCOUNT',
    'Example reference',
    'YOUR_SHOPPER_REFERENCE'
)
    ->billingDate('2021-03-16')
    ->displayedReference('exampleDisplayedReference')
    ->storedPaymentMethodId('8415995487234100')
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postNotifyShopper($body);
    echo 'NotifyShopperResult:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "message": "Request Processed Successfully",
  "resultCode": "Success",
  "shopperNotificationReference": "9915003646742627",
  "storedPaymentMethodId": "8415995487234100",
  "pspReference": "M5N7TQ4TG5PFWR50",
  "reference": "Example reference",
  "displayedReference": "exampleDisplayedReference"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Schedule Account Updater

When making the API call, you can submit either the credit card information, or the recurring detail reference and the shopper reference:

* If the card information is provided, all the sub-fields for `card` are mandatory.
* If the recurring detail reference is provided, the fields for `shopperReference` and `selectedRecurringDetailReference` are mandatory.

```php
function postScheduleAccountUpdater(?ScheduleAccountUpdaterRequest $body = null): ScheduleAccountUpdaterResult
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?ScheduleAccountUpdaterRequest`](../../doc/models/schedule-account-updater-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`ScheduleAccountUpdaterResult`](../../doc/models/schedule-account-updater-result.md)

## Example Usage

```php
$body = ScheduleAccountUpdaterRequestBuilder::init(
    'YOUR_MERCHANT_ACCOUNT',
    'YOUR_REFERENCE'
)
    ->card(
        CardBuilder::init()
            ->expiryMonth('03')
            ->expiryYear('2030')
            ->holderName('Adyen Test')
            ->number('4111111111111111')
            ->build()
    )
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postScheduleAccountUpdater($body);
    echo 'ScheduleAccountUpdaterResult:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "QFQTPCQ8HXSKGK82",
  "result": "Success"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Get 3 Ds Availability

Verifies whether 3D Secure is available for the specified BIN or card brand. For 3D Secure 2, this endpoint also returns device fingerprinting keys.

For more information, refer to [3D Secure 2](https://docs.adyen.com/online-payments/3d-secure/native-3ds2).

```php
function postGet3dsAvailability(?ThreeDSAvailabilityRequest $body = null): ThreeDSAvailabilityResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?ThreeDSAvailabilityRequest`](../../doc/models/three-ds-availability-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`ThreeDSAvailabilityResponse`](../../doc/models/three-ds-availability-response.md)

## Example Usage

```php
$body = ThreeDSAvailabilityRequestBuilder::init(
    'YOUR_MERCHANT_ACCOUNT'
)
    ->cardNumber('4111111111111111')
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postGet3dsAvailability($body);
    echo 'ThreeDSAvailabilityResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "threeDS1Supported": true,
  "threeDS2CardRangeDetails": [],
  "threeDS2supported": false
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Get Cost Estimate

> This API is available only for merchants operating in Australia, the EU, and the UK.

Use the Adyen Cost Estimation API to pre-calculate interchange and scheme fee costs. Knowing these costs prior actual payment authorisation gives you an opportunity to charge those costs to the cardholder, if necessary.

To retrieve this information, make the call to the `/getCostEstimate` endpoint. The response to this call contains the amount of the interchange and scheme fees charged by the network for this transaction, and also which surcharging policy is possible (based on current regulations).

> Since not all information is known in advance (for example, if the cardholder will successfully authenticate via 3D Secure or if you also plan to provide additional Level 2/3 data), the returned amounts are based on a set of assumption criteria you define in the `assumptions` parameter.

```php
function postGetCostEstimate(?CostEstimateRequest $body = null): CostEstimateResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CostEstimateRequest`](../../doc/models/cost-estimate-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CostEstimateResponse`](../../doc/models/cost-estimate-response.md)

## Example Usage

```php
$body = CostEstimateRequestBuilder::init(
    AmountBuilder::init(
        'EUR',
        1234
    )->build(),
    'YOUR_MERCHANT_ACCOUNT'
)
    ->assumptions(
        CostEstimateAssumptions1Builder::init()
            ->assume3DSecureAuthenticated(true)
            ->assumeLevel3Data(true)
            ->build()
    )
    ->cardNumber('5101180000000007')
    ->merchantDetails(
        MerchantDetails2Builder::init()
            ->countryCode('NL')
            ->enrolledIn3DSecure(true)
            ->mcc('7411')
            ->build()
    )
    ->shopperInteraction(ShopperInteractionEnum::ECOMMERCE)
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postGetCostEstimate($body);
    echo 'CostEstimateResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "costEstimateAmount": {
    "currency": "EUR",
    "value": 12
  },
  "resultCode": "Success"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Change Status

Changes the status of the provided payment method to the specified status.

```php
function postChangeStatus(?StoredValueStatusChangeRequest $body = null): StoredValueStatusChangeResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?StoredValueStatusChangeRequest`](../../doc/models/stored-value-status-change-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`StoredValueStatusChangeResponse`](../../doc/models/stored-value-status-change-response.md)

## Example Usage

```php
$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postChangeStatus();
    echo 'StoredValueStatusChangeResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Check Balance

Checks the balance of the provided payment method.

```php
function postCheckBalance(?StoredValueBalanceCheckRequest $body = null): StoredValueBalanceCheckResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?StoredValueBalanceCheckRequest`](../../doc/models/stored-value-balance-check-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`StoredValueBalanceCheckResponse`](../../doc/models/stored-value-balance-check-response.md)

## Example Usage

```php
$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postCheckBalance();
    echo 'StoredValueBalanceCheckResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Issue

Issues a new card of the given payment method.

```php
function postIssue(?StoredValueIssueRequest $body = null): StoredValueIssueResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?StoredValueIssueRequest`](../../doc/models/stored-value-issue-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`StoredValueIssueResponse`](../../doc/models/stored-value-issue-response.md)

## Example Usage

```php
$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postIssue();
    echo 'StoredValueIssueResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Load

Loads the payment method with the specified funds.

```php
function postLoad(?StoredValueLoadRequest $body = null): StoredValueLoadResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?StoredValueLoadRequest`](../../doc/models/stored-value-load-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`StoredValueLoadResponse`](../../doc/models/stored-value-load-response.md)

## Example Usage

```php
$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postLoad();
    echo 'StoredValueLoadResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Merge Balance

Increases the balance of the paymentmethod by the full amount left on the source paymentmethod

```php
function postMergeBalance(?StoredValueBalanceMergeRequest $body = null): StoredValueBalanceMergeResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?StoredValueBalanceMergeRequest`](../../doc/models/stored-value-balance-merge-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`StoredValueBalanceMergeResponse`](../../doc/models/stored-value-balance-merge-response.md)

## Example Usage

```php
$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postMergeBalance();
    echo 'StoredValueBalanceMergeResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Void Transaction

Voids the referenced stored value transaction.

```php
function postVoidTransaction(?StoredValueVoidRequest $body = null): StoredValueVoidResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?StoredValueVoidRequest`](../../doc/models/stored-value-void-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`StoredValueVoidResponse`](../../doc/models/stored-value-void-response.md)

## Example Usage

```php
$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postVoidTransaction();
    echo 'StoredValueVoidResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |


# Post-Request Subject Erasure

Sends the PSP reference containing the shopper data that should be deleted.

```php
function postRequestSubjectErasure(?SubjectErasureByPspReferenceRequest $body = null): SubjectErasureResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?SubjectErasureByPspReferenceRequest`](../../doc/models/subject-erasure-by-psp-reference-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SubjectErasureResponse`](../../doc/models/subject-erasure-response.md)

## Example Usage

```php
$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postRequestSubjectErasure();
    echo 'SubjectErasureResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Create Test Card Ranges

Creates one or more test card ranges.

```php
function postCreateTestCardRanges(?CreateTestCardRangesRequest $body = null): CreateTestCardRangesResult
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CreateTestCardRangesRequest`](../../doc/models/create-test-card-ranges-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CreateTestCardRangesResult`](../../doc/models/create-test-card-ranges-result.md)

## Example Usage

```php
$body = CreateTestCardRangesRequestBuilder::init(
    'accountCode4',
    'accountTypeCode0',
    [
        TestCardRangeBuilder::init(
            'cardHolderName0',
            ExpiryMonthEnum::DECEMBER,
            138,
            'rangeEnd6',
            'rangeStart4'
        )->build()
    ]
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postCreateTestCardRanges($body);
    echo 'CreateTestCardRangesResult:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Create Notification Configuration

Creates a subscription to notifications informing you of events on your platform. After the subscription is created, the events specified in the configuration will be sent to the URL specified in the configuration. Subscriptions must be configured on a per-event basis (as opposed to, for example, a per-account holder basis), so all event notifications of a marketplace and of a given type will be sent to the same endpoint(s). A marketplace may have multiple endpoints if desired; an event notification may be sent to as many or as few different endpoints as configured.

```php
function postCreateNotificationConfiguration(
    ?CreateNotificationConfigurationRequest $body = null
): GetNotificationConfigurationResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CreateNotificationConfigurationRequest`](../../doc/models/create-notification-configuration-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetNotificationConfigurationResponse`](../../doc/models/get-notification-configuration-response.md)

## Example Usage

```php
$body = CreateNotificationConfigurationRequestBuilder::init(
    NotificationConfigurationDetails4Builder::init()
        ->active(true)
        ->description('Unique description 123')
        ->eventConfigs(
            [
                NotificationEventConfigurationBuilder::init(
                    EventTypeEnum::ACCOUNT_HOLDER_VERIFICATION,
                    IncludeModeEnum::INCLUDE_
                )->build()
            ]
        )
        ->notifyPassword('testPassword')
        ->notifyURL('https://www.adyen.com/notification-handler')
        ->notifyUsername('testUserName')
        ->sslProtocol(SslProtocolEnum::TLSV13)
        ->build()
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postCreateNotificationConfiguration($body);
    echo 'GetNotificationConfigurationResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "8516178952380553",
  "configurationDetails": {
    "active": true,
    "description": "Unique description 123",
    "eventConfigs": [
      {
        "eventType": "ACCOUNT_HOLDER_VERIFICATION",
        "includeMode": "INCLUDE"
      }
    ],
    "notificationId": 28468,
    "notifyURL": "https://www.adyen.com/notification-handler",
    "sslProtocol": "TLSv13"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Delete Notification Configurations

Deletes an existing notification subscription configuration. After the subscription is deleted, no further event notifications will be sent to the URL defined in the subscription.

```php
function postDeleteNotificationConfigurations(
    ?DeleteNotificationConfigurationRequest $body = null
): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DeleteNotificationConfigurationRequest`](../../doc/models/delete-notification-configuration-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$body = DeleteNotificationConfigurationRequestBuilder::init(
    [
        27891
    ]
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postDeleteNotificationConfigurations($body);
    echo 'GenericResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "8516480472498802"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Get Notification Configuration

Returns the details of the configuration of a notification subscription.

```php
function postGetNotificationConfiguration(
    ?GetNotificationConfigurationRequest $body = null
): GetNotificationConfigurationResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?GetNotificationConfigurationRequest`](../../doc/models/get-notification-configuration-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetNotificationConfigurationResponse`](../../doc/models/get-notification-configuration-response.md)

## Example Usage

```php
$body = GetNotificationConfigurationRequestBuilder::init(
    21259
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postGetNotificationConfiguration($body);
    echo 'GetNotificationConfigurationResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "8616480378704419",
  "configurationDetails": {
    "active": true,
    "apiVersion": 5,
    "description": "test",
    "eventConfigs": [
      {
        "eventType": "ACCOUNT_HOLDER_VERIFICATION",
        "includeMode": "INCLUDE"
      }
    ],
    "notificationId": 50054,
    "notifyURL": "https://www.adyen.com/notification-handler",
    "sslProtocol": "TLSv13"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Get Notification Configuration List

Returns the details of the configurations of all of the notification subscriptions in the platform of the executing user.

```php
function postGetNotificationConfigurationList(?array $body = null): GetNotificationConfigurationListResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | `?array` | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetNotificationConfigurationListResponse`](../../doc/models/get-notification-configuration-list-response.md)

## Example Usage

```php
$body = ApiHelper::deserialize('{}');

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postGetNotificationConfigurationList($body);
    echo 'GetNotificationConfigurationListResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "8516480437185726",
  "configurations": [
    {
      "active": true,
      "description": "Unique description 12223",
      "eventConfigs": [
        {
          "eventType": "ACCOUNT_HOLDER_VERIFICATION",
          "includeMode": "INCLUDE"
        }
      ],
      "notificationId": 27893,
      "notifyURL": "https://www.adyen.com/notification-handler",
      "sslProtocol": "TLSv13"
    },
    {
      "active": true,
      "description": "just testing things",
      "eventConfigs": [
        {
          "eventType": "ACCOUNT_HOLDER_VERIFICATION",
          "includeMode": "INCLUDE"
        }
      ],
      "notificationId": 25032,
      "notifyURL": "https://www.adyen.com/notification-handler",
      "sslProtocol": "TLSv13"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Test Notification Configuration

Tests an existing notification subscription configuration. For each event type specified, a test notification will be generated and sent to the URL configured in the subscription specified.

```php
function postTestNotificationConfiguration(
    ?TestNotificationConfigurationRequest $body = null
): TestNotificationConfigurationResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?TestNotificationConfigurationRequest`](../../doc/models/test-notification-configuration-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`TestNotificationConfigurationResponse`](../../doc/models/test-notification-configuration-response.md)

## Example Usage

```php
$body = TestNotificationConfigurationRequestBuilder::init(
    25032
)
    ->eventTypes(
        [
            EventType1Enum::ACCOUNT_HOLDER_VERIFICATION
        ]
    )
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postTestNotificationConfiguration($body);
    echo 'TestNotificationConfigurationResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "8616480452462678",
  "errorMessages": [
    "The server did not respond with HTTP 2XX"
  ],
  "eventTypes": [
    "ACCOUNT_HOLDER_VERIFICATION"
  ],
  "exchangeMessages": [
    {
      "messageCode": "Number",
      "messageDescription": "1"
    },
    {
      "messageCode": "Title",
      "messageDescription": "Test 1: 8616480452462678"
    }
  ],
  "notificationId": 25032,
  "okMessages": [
    "...",
    "ResponseTime_ms: 262",
    "ResponseCode: 404"
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Update Notification Configuration

Updates an existing notification subscription configuration. If you are updating the event types, you must provide all event types, otherwise the previous event type configuration will be overwritten.

```php
function postUpdateNotificationConfiguration(
    ?UpdateNotificationConfigurationRequest $body = null
): GetNotificationConfigurationResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?UpdateNotificationConfigurationRequest`](../../doc/models/update-notification-configuration-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetNotificationConfigurationResponse`](../../doc/models/get-notification-configuration-response.md)

## Example Usage

```php
$body = UpdateNotificationConfigurationRequestBuilder::init(
    NotificationConfigurationDetails3Builder::init()
        ->active(false)
        ->description('Test notif config 756')
        ->eventConfigs(
            [
                NotificationEventConfigurationBuilder::init(
                    EventTypeEnum::ACCOUNT_HOLDER_CREATED,
                    IncludeModeEnum::EXCLUDE
                )->build(),
                NotificationEventConfigurationBuilder::init(
                    EventTypeEnum::ACCOUNT_CREATED,
                    IncludeModeEnum::INCLUDE_
                )->build()
            ]
        )
        ->notificationId(21259)
        ->notifyPassword('testPassword2')
        ->notifyURL('https://www.adyen.com/notification-handler')
        ->notifyUsername('testUserName2')
        ->sslProtocol(SslProtocolEnum::TLSV13)
        ->build()
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postUpdateNotificationConfiguration($body);
    echo 'GetNotificationConfigurationResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "8516178952580574",
  "configurationDetails": {
    "active": false,
    "description": "Test notif config 756",
    "eventConfigs": [
      {
        "eventType": "ACCOUNT_CREATED",
        "includeMode": "INCLUDE"
      },
      {
        "eventType": "ACCOUNT_HOLDER_CREATED",
        "includeMode": "EXCLUDE"
      }
    ],
    "notificationId": 21259,
    "notifyURL": "https://www.adyen.com/notification-handler",
    "sslProtocol": "TLSv13"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Account Holder Balance

Returns the account balances of an account holder. An account's balances are organized according by currencies. This mean that an account may have multiple balances: one for each currency.

```php
function postAccountHolderBalance(?CloseAccountHolderRequest $body = null): AccountHolderBalanceResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CloseAccountHolderRequest`](../../doc/models/close-account-holder-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`AccountHolderBalanceResponse`](../../doc/models/account-holder-balance-response.md)

## Example Usage

```php
$body = CloseAccountHolderRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postAccountHolderBalance($body);
    echo 'AccountHolderBalanceResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Account Holder Transaction List

Returns a list of transactions for an account holder's accounts. You can specify the accounts and transaction statuses to be included on the list. The call returns a maximum of 50 transactions for each account. To retrieve all transactions, you must make another call with the 'page' value incremented. Transactions are listed in chronological order, with the most recent transaction first.

```php
function postAccountHolderTransactionList(
    ?AccountHolderTransactionListRequest $body = null
): AccountHolderTransactionListResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?AccountHolderTransactionListRequest`](../../doc/models/account-holder-transaction-list-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`AccountHolderTransactionListResponse`](../../doc/models/account-holder-transaction-list-response.md)

## Example Usage

```php
$body = AccountHolderTransactionListRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER'
)
    ->transactionListsPerAccount(
        [
            TransactionListForAccountBuilder::init(
                '195752115',
                1
            )->build()
        ]
    )->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postAccountHolderTransactionList($body);
    echo 'AccountHolderTransactionListResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Debit Account Holder

Sends a direct debit request to an account holder's bank account. If the direct debit is successful, the funds are settled in the accounts specified in the split instructions. Adyen sends the result of the direct debit in a [`DIRECT_DEBIT_INITIATED`](https://docs.adyen.com/api-explorer/#/NotificationService/latest/post/DIRECT_DEBIT_INITIATED) notification webhook.

To learn more about direct debits, see [Top up accounts](https://docs.adyen.com/classic-platforms/top-up-accounts).

```php
function postDebitAccountHolder(?DebitAccountHolderRequest $body = null): DebitAccountHolderResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DebitAccountHolderRequest`](../../doc/models/debit-account-holder-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`DebitAccountHolderResponse`](../../doc/models/debit-account-holder-response.md)

## Example Usage

```php
$body = DebitAccountHolderRequestBuilder::init(
    'ACCOUNT_HOLDER_CODE',
    AmountBuilder::init(
        'USD',
        6200
    )->build(),
    '000b81aa-ae7e-4492-aa7e-72b2129dce0c',
    'YOUR_MERCHANT_ACCOUNT',
    [
        Split1Builder::init(
            Type60Enum::MARKETPLACE
        )
            ->account('8535516988037431')
            ->amount(
                SplitAmountBuilder::init(
                    6000
                )->build()
            )
            ->reference('YOUR_SPLIT_REFERENCE_1')
            ->build(),
        Split1Builder::init(
            Type60Enum::COMMISSION
        )
            ->amount(
                SplitAmountBuilder::init(
                    200
                )->build()
            )
            ->reference('YOUR_SPLIT_REFERENCE_2')
            ->build()
    ]
)
    ->description('YOUR_DESCRIPTION')
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postDebitAccountHolder($body);
    echo 'DebitAccountHolderResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Payout Account Holder

Pays out a specified amount from an account to the bank account of account holder.

```php
function postPayoutAccountHolder(?PayoutAccountHolderRequest $body = null): PayoutAccountHolderResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?PayoutAccountHolderRequest`](../../doc/models/payout-account-holder-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`PayoutAccountHolderResponse`](../../doc/models/payout-account-holder-response.md)

## Example Usage

```php
$body = PayoutAccountHolderRequestBuilder::init(
    '118731451',
    'CODE_OF_ACCOUNT_HOLDER'
)
    ->amount(
        AmountBuilder::init(
            'EUR',
            99792
        )->build()
    )
    ->bankAccountUUID('000b81aa-ae7e-4492-aa7e-72b2129dce0c')
    ->description('12345 – Test')
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postPayoutAccountHolder($body);
    echo 'PayoutAccountHolderResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Refund Funds Transfer

Refunds funds transferred from one account to another. Both accounts must be in the same platform, but can have different account holders.

```php
function postRefundFundsTransfer(?RefundFundsTransferRequest $body = null): RefundFundsTransferResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?RefundFundsTransferRequest`](../../doc/models/refund-funds-transfer-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`RefundFundsTransferResponse`](../../doc/models/refund-funds-transfer-response.md)

## Example Usage

```php
$body = RefundFundsTransferRequestBuilder::init(
    AmountBuilder::init(
        'EUR',
        1000
    )->build(),
    'PSP_REFERENCE_OF_TRANSFER_TO_REFUND'
)
    ->merchantReference('YOUR_REFERENCE_ID')
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postRefundFundsTransfer($body);
    echo 'RefundFundsTransferResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Refund Not Paid Out Transfers

Refunds all the transactions of an account that have taken place since the most recent payout. This request is on a account basis (as opposed to a payment basis), so only the portion of the payment that was made to the specified account is refunded. The commissions, fees, and payments to other accounts remain in the accounts to which they were sent as designated by the original payment's split details.

```php
function postRefundNotPaidOutTransfers(?RefundNotPaidOutTransfersRequest $body = null): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?RefundNotPaidOutTransfersRequest`](../../doc/models/refund-not-paid-out-transfers-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$body = RefundNotPaidOutTransfersRequestBuilder::init(
    '189184578',
    'CODE_OF_ACCOUNT_HOLDER'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postRefundNotPaidOutTransfers($body);
    echo 'GenericResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Setup Beneficiary

Defines a benefactor and a beneficiary relationship between two accounts. At the time of benefactor/beneficiary setup, the funds in the benefactor account are transferred to the beneficiary account, and any further payments to the benefactor account are automatically sent to the beneficiary account. A series of benefactor/beneficiaries may not exceed four beneficiaries and may not have a cycle in it.

```php
function postSetupBeneficiary(?SetupBeneficiaryRequest $body = null): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?SetupBeneficiaryRequest`](../../doc/models/setup-beneficiary-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$body = SetupBeneficiaryRequestBuilder::init(
    '128952522',
    '134498192'
)
    ->merchantReference('YOUR_REFERENCE_ID')
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postSetupBeneficiary($body);
    echo 'GenericResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Transfer Funds

Transfers funds from one account to another account. Both accounts must be in the same platform, but can have different account holders. The transfer must include a transfer code, which should be determined by the platform, in compliance with local regulations.

```php
function postTransferFunds(?TransferFundsRequest $body = null): TransferFundsResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?TransferFundsRequest`](../../doc/models/transfer-funds-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`TransferFundsResponse`](../../doc/models/transfer-funds-response.md)

## Example Usage

```php
$body = TransferFundsRequestBuilder::init(
    AmountBuilder::init(
        'EUR',
        2000
    )->build(),
    '190324759',
    '100000000',
    'TransferCode_1'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postTransferFunds($body);
    echo 'TransferFundsResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Accept Dispute

Accepts a specific dispute.

```php
function postAcceptDispute(?AcceptDisputeRequest $body = null): AcceptDisputeResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?AcceptDisputeRequest`](../../doc/models/accept-dispute-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`AcceptDisputeResponse`](../../doc/models/accept-dispute-response.md)

## Example Usage

```php
$body = AcceptDisputeRequestBuilder::init(
    'DZ4DPSHB4WD2WN82',
    'YOUR_MERCHANT_ACCOUNT'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postAcceptDispute($body);
    echo 'AcceptDisputeResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "disputeServiceResult": {
    "success": true
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Defend Dispute

Defends a specific dispute.

```php
function postDefendDispute(?DefendDisputeRequest $body = null): DefendDisputeResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DefendDisputeRequest`](../../doc/models/defend-dispute-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`DefendDisputeResponse`](../../doc/models/defend-dispute-response.md)

## Example Usage

```php
$body = DefendDisputeRequestBuilder::init(
    'SupplyDefenseMaterial',
    'DZ4DPSHB4WD2WN82',
    'YOUR_MERCHANT_ACCOUNT'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postDefendDispute($body);
    echo 'DefendDisputeResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "disputeServiceResult": {
    "success": true
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Delete Dispute Defense Document

Deletes a specific dispute defense document that was supplied earlier.

```php
function postDeleteDisputeDefenseDocument(
    ?DeleteDefenseDocumentRequest $body = null
): DeleteDefenseDocumentResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DeleteDefenseDocumentRequest`](../../doc/models/delete-defense-document-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`DeleteDefenseDocumentResponse`](../../doc/models/delete-defense-document-response.md)

## Example Usage

```php
$body = DeleteDefenseDocumentRequestBuilder::init(
    'DefenseMaterial',
    'DZ4DPSHB4WD2WN82',
    'YOUR_MERCHANT_ACCOUNT'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postDeleteDisputeDefenseDocument($body);
    echo 'DeleteDefenseDocumentResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "disputeServiceResult": {
    "success": true
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Retrieve Applicable Defense Reasons

Returns a list of all applicable defense reasons to defend a specific dispute.

```php
function postRetrieveApplicableDefenseReasons(?DefenseReasonsRequest $body = null): DefenseReasonsResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DefenseReasonsRequest`](../../doc/models/defense-reasons-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`DefenseReasonsResponse`](../../doc/models/defense-reasons-response.md)

## Example Usage

```php
$body = DefenseReasonsRequestBuilder::init(
    'DZ4DPSHB4WD2WN82',
    'YOUR_MERCHANT_ACCOUNT'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postRetrieveApplicableDefenseReasons($body);
    echo 'DefenseReasonsResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "defenseReasons": [
    {
      "defenseDocumentTypes": [
        {
          "available": false,
          "defenseDocumentTypeCode": "TIDorInvoice",
          "requirementLevel": "Optional"
        },
        {
          "available": false,
          "defenseDocumentTypeCode": "GoodsNotReturned",
          "requirementLevel": "Required"
        }
      ],
      "defenseReasonCode": "GoodsNotReturned",
      "satisfied": false
    },
    {
      "defenseDocumentTypes": [
        {
          "available": false,
          "defenseDocumentTypeCode": "TIDorInvoice",
          "requirementLevel": "Optional"
        },
        {
          "available": false,
          "defenseDocumentTypeCode": "GoodsRepairedOrReplaced",
          "requirementLevel": "Required"
        }
      ],
      "defenseReasonCode": "GoodsRepairedOrReplaced",
      "satisfied": false
    },
    {
      "defenseDocumentTypes": [
        {
          "available": false,
          "defenseDocumentTypeCode": "GoodsWereAsDescribed",
          "requirementLevel": "Required"
        },
        {
          "available": false,
          "defenseDocumentTypeCode": "TIDorInvoice",
          "requirementLevel": "Required"
        }
      ],
      "defenseReasonCode": "GoodsWereAsDescribed",
      "satisfied": false
    },
    {
      "defenseDocumentTypes": [
        {
          "available": false,
          "defenseDocumentTypeCode": "TIDorInvoice",
          "requirementLevel": "Optional"
        },
        {
          "available": false,
          "defenseDocumentTypeCode": "DefenseMaterial",
          "requirementLevel": "Required"
        }
      ],
      "defenseReasonCode": "SupplyDefenseMaterial",
      "satisfied": false
    }
  ],
  "disputeServiceResult": {
    "success": true
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Supply Defense Document

Supplies a specific dispute defense document.

```php
function postSupplyDefenseDocument(?SupplyDefenseDocumentRequest $body = null): SupplyDefenseDocumentResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?SupplyDefenseDocumentRequest`](../../doc/models/supply-defense-document-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SupplyDefenseDocumentResponse`](../../doc/models/supply-defense-document-response.md)

## Example Usage

```php
$body = SupplyDefenseDocumentRequestBuilder::init(
    [
        DefenseDocumentBuilder::init(
            'JVBERi0xLjQKJcOkw7zDtsOfCjIgMCBv+f/ub0j6JPRX+E3EmC==',
            'application/pdf',
            'DefenseMaterial'
        )->build()
    ],
    'DZ4DPSHB4WD2WN82',
    'YOUR_MERCHANT_ACCOUNT'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postSupplyDefenseDocument($body);
    echo 'SupplyDefenseDocumentResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "disputeServiceResult": {
    "success": true
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Sessions

**This endpoint is deprecated.**

Establishes a secure communications session between the POS Mobile SDK and the Adyen payments platform, through mutual authentication.
The request sends a setup token that identifies the SDK and the device. The response returns a session token that the SDK can use to authenticate responses received from the Adyen payments platform.

> This request applies to **mobile in-person** transactions. You cannot use this request to create online payments sessions.

```php
function postSessions(?CreateSessionRequest $body = null): CertificateLoadingResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CreateSessionRequest`](../../doc/models/create-session-request.md) | Body, Optional | - |

## Response Type

**201**: Created - the request has been fulfilled and has resulted in one or more new resources being created.

[`CertificateLoadingResponse`](../../doc/models/certificate-loading-response.md)

## Example Usage

```php
$body = CreateSessionRequestBuilder::init(
    'YOUR_MERCHANT_ACCOUNT',
    'SETUP_TOKEN'
)
    ->store('YOUR_STORE_ID')
    ->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postSessions($body);
    echo 'CertificateLoadingResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "APP_SESSION_ID",
  "installationId": "INSTALLATION_ID",
  "merchantAccount": "YOUR_MERCHANT_ACCOUNT",
  "store": "YOUR_STORE_ID",
  "sdkData": "SDK_DATA_BLOB"
}
```


# Post-Assign Terminals

**This endpoint is deprecated.**

Assigns one or more payment terminals to a merchant account or a store. You can also use this endpoint to reassign terminals between merchant accounts or stores, and to unassign a terminal and return it to company inventory.

> From January 1, 2025 POS Terminal Management API is deprecated and support stops on April 1, 2025. To automate the management of your terminal fleet, use our [Management API](https://docs.adyen.com/api-explorer/Management/latest/overview).

```php
function postAssignTerminals(?AssignTerminalsRequest $body = null): AssignTerminalsResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?AssignTerminalsRequest`](../../doc/models/assign-terminals-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`AssignTerminalsResponse`](../../doc/models/assign-terminals-response.md)

## Example Usage

```php
$body = AssignTerminalsRequestBuilder::init(
    'YOUR_COMPANY_ACCOUNT',
    [
        'P400Plus-275479597'
    ]
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postAssignTerminals($body);
    echo 'AssignTerminalsResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "results": {
    "P400Plus-275479597": "RemoveConfigScheduled"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Find Terminal

**This endpoint is deprecated.**

Returns the company account, merchant account, or store that a payment terminal is assigned to.

> From January 1, 2025 POS Terminal Management API is deprecated and support stops on April 1, 2025. To automate the management of your terminal fleet, use our [Management API](https://docs.adyen.com/api-explorer/Management/latest/overview).

```php
function postFindTerminal(?FindTerminalRequest $body = null): FindTerminalResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?FindTerminalRequest`](../../doc/models/find-terminal-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`FindTerminalResponse`](../../doc/models/find-terminal-response.md)

## Example Usage

```php
$body = FindTerminalRequestBuilder::init(
    'M400-401972715'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postFindTerminal($body);
    echo 'FindTerminalResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "companyAccount": "YOUR_COMPANY_ACCOUNT",
  "merchantAccount": "YOUR_MERCHANT_ACCOUNT",
  "merchantInventory": false,
  "store": "YOUR_STORE",
  "terminal": "M400-401972715"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Get Stores Under Account

**This endpoint is deprecated.**

Returns a list of stores associated with a company account or a merchant account, including the status of each store.

> From January 1, 2025 POS Terminal Management API is deprecated and support stops on April 1, 2025. To automate the management of your terminal fleet, use our [Management API](https://docs.adyen.com/api-explorer/Management/latest/overview).

```php
function postGetStoresUnderAccount(?GetStoresUnderAccountRequest $body = null): GetStoresUnderAccountResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?GetStoresUnderAccountRequest`](../../doc/models/get-stores-under-account-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetStoresUnderAccountResponse`](../../doc/models/get-stores-under-account-response.md)

## Example Usage

```php
$body = GetStoresUnderAccountRequestBuilder::init(
    'YOUR_COMPANY_ACCOUNT'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postGetStoresUnderAccount($body);
    echo 'GetStoresUnderAccountResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "stores": [
    {
      "store": "YOUR_STORE",
      "description": "YOUR_STORE",
      "address": {
        "city": "The City",
        "countryCode": "NL",
        "postalCode": "1234",
        "streetAddress": "The Street"
      },
      "status": "Active",
      "merchantAccountCode": "YOUR_MERCHANT_ACCOUNT"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Get Terminal Details

**This endpoint is deprecated.**

Returns the details of a payment terminal, including where the terminal is assigned to. The response returns the same details that are provided in the terminal list in your Customer Area and in the Terminal Fleet report.

> From January 1, 2025 POS Terminal Management API is deprecated and support stops on April 1, 2025. To automate the management of your terminal fleet, use our [Management API](https://docs.adyen.com/api-explorer/Management/latest/overview).

```php
function postGetTerminalDetails(?GetTerminalDetailsRequest $body = null): GetTerminalDetailsResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?GetTerminalDetailsRequest`](../../doc/models/get-terminal-details-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetTerminalDetailsResponse`](../../doc/models/get-terminal-details-response.md)

## Example Usage

```php
$body = GetTerminalDetailsRequestBuilder::init(
    'M400-401972715'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postGetTerminalDetails($body);
    echo 'GetTerminalDetailsResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "companyAccount": "YOUR_COMPANY_ACCOUNT",
  "merchantAccount": "YOUR_MERCHANT_ACCOUNT",
  "merchantInventory": false,
  "store": "YOUR_STORE",
  "terminal": "M400-401972715",
  "deviceModel": "M400",
  "serialNumber": "401-972-715",
  "permanentTerminalId": "88912016",
  "terminalStatus": "SwitchedOff",
  "firmwareVersion": "Verifone_VOS 1.57.6",
  "country": "NETHERLANDS",
  "storeDetails": {
    "store": "YOUR_STORE",
    "description": "TestStore",
    "address": {
      "city": "The City",
      "countryCode": "NL",
      "postalCode": "1234",
      "streetAddress": "The Street"
    }
  },
  "ethernetMac": "60:c7:98:5a:69:cd",
  "ethernetIp": "192.168.2.11",
  "wifiMac": "c4:ac:59:47:f3:71",
  "wifiIp": "192.168.2.12",
  "dhcpEnabled": false
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |


# Post-Get Terminals Under Account

**This endpoint is deprecated.**

Returns a list of payment terminals associated with a company account, merchant account, or store. The response shows whether the terminals are in the inventory, or in-store (ready for boarding or already boarded).

> From January 1, 2025 POS Terminal Management API is deprecated and support stops on April 1, 2025. To automate the management of your terminal fleet, use our [Management API](https://docs.adyen.com/api-explorer/Management/latest/overview).

```php
function postGetTerminalsUnderAccount(
    ?GetTerminalsUnderAccountRequest $body = null
): GetTerminalsUnderAccountResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?GetTerminalsUnderAccountRequest`](../../doc/models/get-terminals-under-account-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetTerminalsUnderAccountResponse`](../../doc/models/get-terminals-under-account-response.md)

## Example Usage

```php
$body = GetTerminalsUnderAccountRequestBuilder::init(
    'YOUR_COMPANY_ACCOUNT'
)->build();

$generalApi = $client->getGeneralApi();

try {
    $result = $generalApi->postGetTerminalsUnderAccount($body);
    echo 'GetTerminalsUnderAccountResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "companyAccount": "YOUR_COMPANY_ACCOUNT",
  "merchantAccounts": [
    {
      "merchantAccount": "YOUR_MERCHANT_ACCOUNT",
      "inStoreTerminals": [
        "P400Plus-275479597"
      ],
      "stores": [
        {
          "store": "YOUR_STORE",
          "inStoreTerminals": [
            "M400-401972715"
          ]
        }
      ]
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorError1Exception`](../../doc/models/service-error-error-1-exception.md) |

