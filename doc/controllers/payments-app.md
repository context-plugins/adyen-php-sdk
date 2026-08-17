# Payments App

```php
$paymentsAppApi = $client->getPaymentsAppApi();
```

## Class Name

`PaymentsAppApi`

## Methods

* [Post-Merchants-Merchant Id-Generate Payments App Boarding Token](../../doc/controllers/payments-app.md#post-merchants-merchant-id-generate-payments-app-boarding-token)
* [Post-Merchants-Merchant Id-Stores-Store Id-Generate Payments App Boarding Token](../../doc/controllers/payments-app.md#post-merchants-merchant-id-stores-store-id-generate-payments-app-boarding-token)
* [Get-Merchants-Merchant Id-Payments Apps](../../doc/controllers/payments-app.md#get-merchants-merchant-id-payments-apps)
* [Get-Merchants-Merchant Id-Stores-Store Id-Payments Apps](../../doc/controllers/payments-app.md#get-merchants-merchant-id-stores-store-id-payments-apps)
* [Post-Merchants-Merchant Id-Payments Apps-Installation Id-Revoke](../../doc/controllers/payments-app.md#post-merchants-merchant-id-payments-apps-installation-id-revoke)


# Post-Merchants-Merchant Id-Generate Payments App Boarding Token

Creates a boarding token used to authenticate the installation of a Payments App instance on an Android device. The boarding token is created for the `boardingRequestToken` of the Payments App for the merchant account identified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Adyen Payments App role

:information_source: **Note** This endpoint does not require authentication.

```php
function postMerchantsMerchantIdGeneratePaymentsAppBoardingToken(
    string $merchantId,
    BoardingTokenRequest $body
): BoardingTokenResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account.<br><br>**Constraints**: *Minimum Length*: `1` |
| `body` | [`BoardingTokenRequest`](../../doc/models/boarding-token-request.md) | Body, Required | - |

## Response Type

**200**: OK - the request has succeeded.

[`BoardingTokenResponse`](../../doc/models/boarding-token-response.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$body = BoardingTokenRequestBuilder::init(
    'boardingRequestToken6'
)->build();

$paymentsAppApi = $client->getPaymentsAppApi();

try {
    $result = $paymentsAppApi->postMerchantsMerchantIdGeneratePaymentsAppBoardingToken(
        $merchantId,
        $body
    );
    echo 'BoardingTokenResponse:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Merchants-Merchant Id-Stores-Store Id-Generate Payments App Boarding Token

Creates a boarding token used to authenticate the installation of a Payments App instance on an Android device. The boarding token is created for the `boardingRequestToken` of the Payments App for the store identified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Adyen Payments App role

:information_source: **Note** This endpoint does not require authentication.

```php
function postMerchantsMerchantIdStoresStoreIdGeneratePaymentsAppBoardingToken(
    string $merchantId,
    string $storeId,
    BoardingTokenRequest $body
): BoardingTokenResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account.<br><br>**Constraints**: *Minimum Length*: `1` |
| `storeId` | `string` | Template, Required | The unique identifier of the store.<br><br>**Constraints**: *Minimum Length*: `1` |
| `body` | [`BoardingTokenRequest`](../../doc/models/boarding-token-request.md) | Body, Required | - |

## Response Type

**200**: OK - the request has succeeded.

[`BoardingTokenResponse`](../../doc/models/boarding-token-response.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$storeId = 'storeId6';

$body = BoardingTokenRequestBuilder::init(
    'boardingRequestToken6'
)->build();

$paymentsAppApi = $client->getPaymentsAppApi();

try {
    $result = $paymentsAppApi->postMerchantsMerchantIdStoresStoreIdGeneratePaymentsAppBoardingToken(
        $merchantId,
        $storeId,
        $body
    );
    echo 'BoardingTokenResponse:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Merchants-Merchant Id-Payments Apps

Returns the list of Payments App instances for the merchant account identified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Adyen Payments App role

:information_source: **Note** This endpoint does not require authentication.

```php
function getMerchantsMerchantIdPaymentsApps(
    string $merchantId,
    ?string $statuses = null,
    ?int $limit = 10,
    ?int $offset = 0
): PaymentsAppResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account.<br><br>**Constraints**: *Minimum Length*: `1` |
| `statuses` | `?string` | Query, Optional | The status of the Payments App. Comma-separated list of one or more values. If no value is provided, the list returns all statuses.<br><br>Possible values:<br><br>* **BOARDING**<br><br>* **BOARDED**<br><br>* **REVOKED** |
| `limit` | `?int` | Query, Optional | The number of items to return.<br><br>**Default**: `10`<br><br>**Constraints**: `<= 100` |
| `offset` | `?int` | Query, Optional | The number of items to skip.<br><br>**Default**: `0` |

## Response Type

**200**: OK - the request has succeeded.

[`PaymentsAppResponse`](../../doc/models/payments-app-response.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$limit = 10;

$offset = 0;

$paymentsAppApi = $client->getPaymentsAppApi();

try {
    $result = $paymentsAppApi->getMerchantsMerchantIdPaymentsApps(
        $merchantId,
        null,
        $limit,
        $offset
    );
    echo 'PaymentsAppResponse:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Merchants-Merchant Id-Stores-Store Id-Payments Apps

Returns the list of Payments App instances for the store identified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Adyen Payments App role

:information_source: **Note** This endpoint does not require authentication.

```php
function getMerchantsMerchantIdStoresStoreIdPaymentsApps(
    string $merchantId,
    string $storeId,
    ?string $statuses = null,
    ?int $limit = 10,
    ?int $offset = 0
): PaymentsAppResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account.<br><br>**Constraints**: *Minimum Length*: `1` |
| `storeId` | `string` | Template, Required | The unique identifier of the store.<br><br>**Constraints**: *Minimum Length*: `1` |
| `statuses` | `?string` | Query, Optional | The status of the Payments App. Comma-separated list of one or more values. If no value is provided, the list returns all statuses.<br><br>Possible values:<br><br>* **BOARDING**<br><br>* **BOARDED**<br><br>* **REVOKED** |
| `limit` | `?int` | Query, Optional | The number of items to return.<br><br>**Default**: `10`<br><br>**Constraints**: `<= 100` |
| `offset` | `?int` | Query, Optional | The number of items to skip.<br><br>**Default**: `0` |

## Response Type

**200**: OK - the request has succeeded.

[`PaymentsAppResponse`](../../doc/models/payments-app-response.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$storeId = 'storeId6';

$limit = 10;

$offset = 0;

$paymentsAppApi = $client->getPaymentsAppApi();

try {
    $result = $paymentsAppApi->getMerchantsMerchantIdStoresStoreIdPaymentsApps(
        $merchantId,
        $storeId,
        null,
        $limit,
        $offset
    );
    echo 'PaymentsAppResponse:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Merchants-Merchant Id-Payments Apps-Installation Id-Revoke

Revokes the authentication of the Payments App instance for the `installationId` and merchant account identified in the path. This call revokes the authentication of the Payments App instance with the `installationId` identified in the path for both merchant accounts and stores.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Adyen Payments App role

:information_source: **Note** This endpoint does not require authentication.

```php
function postMerchantsMerchantIdPaymentsAppsInstallationIdRevoke(string $merchantId, string $installationId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account.<br><br>**Constraints**: *Minimum Length*: `1` |
| `installationId` | `string` | Template, Required | The unique identifier of the Payments App instance on a device.<br><br>**Constraints**: *Minimum Length*: `1` |

## Response Type

**200**: OK - the request has succeeded.

`mixed`

## Example Usage

```php
$merchantId = 'merchantId6';

$installationId = 'installationId4';

$paymentsAppApi = $client->getPaymentsAppApi();

try {
    $result = $paymentsAppApi->postMerchantsMerchantIdPaymentsAppsInstallationIdRevoke(
        $merchantId,
        $installationId
    );
    echo 'mixed:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

