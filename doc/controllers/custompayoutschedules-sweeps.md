# Custompayoutschedules Sweeps

```php
$custompayoutschedulesSweepsApi = $client->getCustompayoutschedulesSweepsApi();
```

## Class Name

`CustompayoutschedulesSweepsApi`

## Methods

* [Get-Balance Accounts-Balance Account Id-Sweeps](../../doc/controllers/custompayoutschedules-sweeps.md#get-balance-accounts-balance-account-id-sweeps)
* [Post-Balance Accounts-Balance Account Id-Sweeps](../../doc/controllers/custompayoutschedules-sweeps.md#post-balance-accounts-balance-account-id-sweeps)
* [Get-Balance Accounts-Balance Account Id-Sweeps-Sweep Id](../../doc/controllers/custompayoutschedules-sweeps.md#get-balance-accounts-balance-account-id-sweeps-sweep-id)
* [Delete-Balance Accounts-Balance Account Id-Sweeps-Sweep Id](../../doc/controllers/custompayoutschedules-sweeps.md#delete-balance-accounts-balance-account-id-sweeps-sweep-id)
* [Patch-Balance Accounts-Balance Account Id-Sweeps-Sweep Id](../../doc/controllers/custompayoutschedules-sweeps.md#patch-balance-accounts-balance-account-id-sweeps-sweep-id)


# Get-Balance Accounts-Balance Account Id-Sweeps

Returns a list of the sweeps configured for a balance account.

To fetch multiple pages, use the query parameters. For example, to limit the page to 5 sweeps and to skip the first 10, use `/balanceAccounts/{balanceAccountId}/sweeps?limit=5&offset=10`.

```php
function getBalanceAccountsBalanceAccountIdSweeps(
    string $balanceAccountId,
    ?int $offset = null,
    ?int $limit = null
): BalanceSweepConfigurationsResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `offset` | `?int` | Query, Optional | The number of items that you want to skip. |
| `limit` | `?int` | Query, Optional | The number of items returned per page, maximum 100 items. By default, the response returns 10 items per page. |

## Response Type

**200**: OK - the request has succeeded.

[`BalanceSweepConfigurationsResponse`](../../doc/models/balance-sweep-configurations-response.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$customPayoutSchedulesSweepsApi = $client->getCustomPayoutSchedulesSweepsApi();

try {
    $result = $customPayoutSchedulesSweepsApi->getBalanceAccountsBalanceAccountIdSweeps($balanceAccountId);
    echo 'BalanceSweepConfigurationsResponse:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "hasNext": false,
  "hasPrevious": false,
  "sweeps": [
    {
      "id": "SWPC4227C224555B5FTD2NT2JV4WN5",
      "schedule": {
        "type": "daily"
      },
      "status": "active",
      "targetAmount": {
        "currency": "EUR",
        "value": 0
      },
      "triggerAmount": {
        "currency": "EUR",
        "value": 0
      },
      "type": "push",
      "counterparty": {
        "balanceAccountId": "BA32272223222B5FTD2KR6TJD"
      },
      "currency": "EUR"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |


# Post-Balance Accounts-Balance Account Id-Sweeps

Creates a sweep that results in moving funds from or to a balance account.

A sweep pulls in or pushes out funds based on a defined schedule, amount, currency, and a source or a destination.

```php
function postBalanceAccountsBalanceAccountIdSweeps(
    string $balanceAccountId,
    ?CreateSweepConfigurationV2 $body = null
): SweepConfigurationV2
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `body` | [`?CreateSweepConfigurationV2`](../../doc/models/create-sweep-configuration-v2.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SweepConfigurationV2`](../../doc/models/sweep-configuration-v2.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$body = CreateSweepConfigurationV2Builder::init(
    SweepCounterparty1Builder::init()
        ->merchantAccount('YOUR_MERCHANT_ACCOUNT')
        ->build(),
    'EUR',
    SweepSchedule1Builder::init(
        Type62Enum::BALANCE
    )->build()
)
    ->status(Status6Enum::ACTIVE)
    ->triggerAmount(
        Amount17Builder::init(
            'EUR',
            50000
        )->build()
    )
    ->type(Type72Enum::PULL)
    ->build();

$customPayoutSchedulesSweepsApi = $client->getCustomPayoutSchedulesSweepsApi();

try {
    $result = $customPayoutSchedulesSweepsApi->postBalanceAccountsBalanceAccountIdSweeps(
        $balanceAccountId,
        $body
    );
    echo 'SweepConfigurationV2:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "SWPC4227C224555B5FTD2NT2JV4WN5",
  "counterparty": {
    "merchantAccount": "YOUR_MERCHANT_ACCOUNT"
  },
  "triggerAmount": {
    "currency": "EUR",
    "value": 50000
  },
  "currency": "EUR",
  "schedule": {
    "type": "balance"
  },
  "type": "pull",
  "status": "active"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |


# Get-Balance Accounts-Balance Account Id-Sweeps-Sweep Id

Returns a sweep.

```php
function getBalanceAccountsBalanceAccountIdSweepsSweepId(
    string $balanceAccountId,
    string $sweepId
): SweepConfigurationV2
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `sweepId` | `string` | Template, Required | The unique identifier of the sweep. |

## Response Type

**200**: OK - the request has succeeded.

[`SweepConfigurationV2`](../../doc/models/sweep-configuration-v2.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$sweepId = 'sweepId4';

$customPayoutSchedulesSweepsApi = $client->getCustomPayoutSchedulesSweepsApi();

try {
    $result = $customPayoutSchedulesSweepsApi->getBalanceAccountsBalanceAccountIdSweepsSweepId(
        $balanceAccountId,
        $sweepId
    );
    echo 'SweepConfigurationV2:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "SWPC4227C224555B5FTD2NT2JV4WN5",
  "schedule": {
    "type": "daily"
  },
  "status": "active",
  "targetAmount": {
    "currency": "EUR",
    "value": 0
  },
  "triggerAmount": {
    "currency": "EUR",
    "value": 0
  },
  "type": "push",
  "counterparty": {
    "balanceAccountId": "BA32272223222B5FTD2KR6TJD"
  },
  "currency": "EUR"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |


# Delete-Balance Accounts-Balance Account Id-Sweeps-Sweep Id

Deletes a sweep for a balance account.

```php
function deleteBalanceAccountsBalanceAccountIdSweepsSweepId(string $balanceAccountId, string $sweepId): void
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `sweepId` | `string` | Template, Required | The unique identifier of the sweep. |

## Response Type

**204**: No Content - look at the actual response code for the status of the request.

`void`

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$sweepId = 'sweepId4';

$customPayoutSchedulesSweepsApi = $client->getCustomPayoutSchedulesSweepsApi();

try {
    $customPayoutSchedulesSweepsApi->deleteBalanceAccountsBalanceAccountIdSweepsSweepId(
        $balanceAccountId,
        $sweepId
    );
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |


# Patch-Balance Accounts-Balance Account Id-Sweeps-Sweep Id

Updates a sweep. When updating a sweep resource, note that if a request parameter is not provided, the parameter is left unchanged.

```php
function patchBalanceAccountsBalanceAccountIdSweepsSweepId(
    string $balanceAccountId,
    string $sweepId,
    ?UpdateSweepConfigurationV2 $body = null
): SweepConfigurationV2
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `sweepId` | `string` | Template, Required | The unique identifier of the sweep. |
| `body` | [`?UpdateSweepConfigurationV2`](../../doc/models/update-sweep-configuration-v2.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SweepConfigurationV2`](../../doc/models/sweep-configuration-v2.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$sweepId = 'sweepId4';

$body = UpdateSweepConfigurationV2Builder::init()
    ->status(Status6Enum::INACTIVE)
    ->build();

$customPayoutSchedulesSweepsApi = $client->getCustomPayoutSchedulesSweepsApi();

try {
    $result = $customPayoutSchedulesSweepsApi->patchBalanceAccountsBalanceAccountIdSweepsSweepId(
        $balanceAccountId,
        $sweepId,
        $body
    );
    echo 'SweepConfigurationV2:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "SWPC4227C224555B5FTD2NT2JV4WN5",
  "counterparty": {
    "merchantAccount": "YOUR_MERCHANT_ACCOUNT"
  },
  "triggerAmount": {
    "currency": "EUR",
    "value": 50000
  },
  "currency": "EUR",
  "schedule": {
    "type": "balance"
  },
  "type": "pull",
  "status": "inactive"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |

