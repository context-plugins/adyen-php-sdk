# Managedpayoutschedules

```php
$managedpayoutschedulesApi = $client->getManagedpayoutschedulesApi();
```

## Class Name

`ManagedpayoutschedulesApi`

## Methods

* [Get-Balance Accounts-Balance Account Id-Payout Schedules](../../doc/controllers/managedpayoutschedules.md#get-balance-accounts-balance-account-id-payout-schedules)
* [Post-Balance Accounts-Balance Account Id-Payout Schedules](../../doc/controllers/managedpayoutschedules.md#post-balance-accounts-balance-account-id-payout-schedules)
* [Get-Balance Accounts-Balance Account Id-Payout Schedules-Id](../../doc/controllers/managedpayoutschedules.md#get-balance-accounts-balance-account-id-payout-schedules-id)
* [Delete-Balance Accounts-Balance Account Id-Payout Schedules-Id](../../doc/controllers/managedpayoutschedules.md#delete-balance-accounts-balance-account-id-payout-schedules-id)
* [Patch-Balance Accounts-Balance Account Id-Payout Schedules-Id](../../doc/controllers/managedpayoutschedules.md#patch-balance-accounts-balance-account-id-payout-schedules-id)
* [Get-Balance Accounts-Balance Account Id-Payout Schedules-Id-Executions](../../doc/controllers/managedpayoutschedules.md#get-balance-accounts-balance-account-id-payout-schedules-id-executions)
* [Get-Balance Platforms-Balance Platform Id-Payout Schedules](../../doc/controllers/managedpayoutschedules.md#get-balance-platforms-balance-platform-id-payout-schedules)
* [Get-Balance Platforms-Balance Platform Id-Payout Schedules-Id](../../doc/controllers/managedpayoutschedules.md#get-balance-platforms-balance-platform-id-payout-schedules-id)


# Get-Balance Accounts-Balance Account Id-Payout Schedules

Returns a list of all managed payout schedules that are configured on a balance account. You can use query parameters to filter the elements that are returned in the list.

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalanceAccountsBalanceAccountIdPayoutSchedules(
    string $balanceAccountId,
    ?string $currency = null,
    ?string $cursor = null,
    ?int $limit = 10
): BalanceAccountConfigurations
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `currency` | `?string` | Query, Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes) of the currency used in the payout schedule. |
| `cursor` | `?string` | Query, Optional | The `cursor` returned in the links of the previous response. |
| `limit` | `?int` | Query, Optional | The number of items returned per page, maximum of 100 items. By default, the response returns 10 items per page.<br><br>**Default**: `10`<br><br>**Constraints**: `>= 1`, `<= 100` |

## Response Type

**200**: OK - The request has succeeded.

[`BalanceAccountConfigurations`](../../doc/models/balance-account-configurations.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$limit = 10;

$managedPayoutSchedulesApi = $client->getManagedPayoutSchedulesApi();

try {
    $result = $managedPayoutSchedulesApi->getBalanceAccountsBalanceAccountIdPayoutSchedules(
        $balanceAccountId,
        null,
        null,
        $limit
    );
    echo 'BalanceAccountConfigurations:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "balanceAccountPayoutSchedules": [
    {
      "id": "PSAC00000000000000000000000001",
      "balancePlatformPayoutScheduleId": "PSPC00000000000000000000000001",
      "balanceAccountId": "BA000000000000000000001",
      "transferInstrumentId": "SE00000000000000000000001",
      "currency": "EUR",
      "reference": "Monthly payout",
      "description": "Scheduled payout to merchant bank account",
      "referenceForBeneficiary": "PAYOUT-REF-001",
      "retainedAmount": 10000,
      "minPayoutAmount": 1000,
      "maxPayoutAmount": 100000000,
      "createdAt": "2024-01-15T10:30:00Z",
      "enabled": true,
      "frequency": "monthly",
      "frequencyValue": 1
    }
  ],
  "link": {
    "next": {
      "href": "/balanceAccounts/BA000000000000000000001/payoutSchedules?limit=10"
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the resource was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Balance Accounts-Balance Account Id-Payout Schedules

Apply a managed payout schedule to a balance account. This payout schedule is based on an existing payout schedule in your balance platform.

:information_source: **Note** This endpoint does not require authentication.

```php
function postBalanceAccountsBalanceAccountIdPayoutSchedules(
    string $balanceAccountId,
    BalanceAccountConfigurationRequest $body
): BalanceAccountConfiguration
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `body` | [`BalanceAccountConfigurationRequest`](../../doc/models/balance-account-configuration-request.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`BalanceAccountConfiguration`](../../doc/models/balance-account-configuration.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$body = BalanceAccountConfigurationRequestBuilder::init(
    'PSPC00000000000000000000000001',
    Frequency1Enum::MONTHLY,
    'SE00000000000000000000001'
)
    ->currency('EUR')
    ->description('Scheduled payout to merchant bank account')
    ->enabled(true)
    ->frequencyValue(1)
    ->maxPayoutAmount(100000000)
    ->minPayoutAmount(1000)
    ->reference('Monthly payout')
    ->referenceForBeneficiary('PAYOUT-REF-001')
    ->retainedAmount(10000)
    ->build();

$managedPayoutSchedulesApi = $client->getManagedPayoutSchedulesApi();

try {
    $result = $managedPayoutSchedulesApi->postBalanceAccountsBalanceAccountIdPayoutSchedules(
        $balanceAccountId,
        $body
    );
    echo 'BalanceAccountConfiguration:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "PSAC00000000000000000000000001",
  "balancePlatformPayoutScheduleId": "PSPC00000000000000000000000001",
  "balanceAccountId": "BA000000000000000000001",
  "transferInstrumentId": "SE00000000000000000000001",
  "currency": "EUR",
  "reference": "Monthly payout",
  "description": "Scheduled payout to merchant bank account",
  "referenceForBeneficiary": "PAYOUT-REF-001",
  "retainedAmount": 10000,
  "minPayoutAmount": 1000,
  "maxPayoutAmount": 100000000,
  "createdAt": "2024-01-15T10:30:00Z",
  "enabled": true,
  "frequency": "monthly",
  "frequencyValue": 1
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the resource was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Balance Accounts-Balance Account Id-Payout Schedules-Id

Returns the specified payout schedule.

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalanceAccountsBalanceAccountIdPayoutSchedulesId(
    string $balanceAccountId,
    string $id
): BalanceAccountConfiguration
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `id` | `string` | Template, Required | The unique identifier of the payout schedule for the balance account. |

## Response Type

**200**: OK - The request has succeeded.

[`BalanceAccountConfiguration`](../../doc/models/balance-account-configuration.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$id = 'id0';

$managedPayoutSchedulesApi = $client->getManagedPayoutSchedulesApi();

try {
    $result = $managedPayoutSchedulesApi->getBalanceAccountsBalanceAccountIdPayoutSchedulesId(
        $balanceAccountId,
        $id
    );
    echo 'BalanceAccountConfiguration:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "PSAC00000000000000000000000001",
  "balancePlatformPayoutScheduleId": "PSPC00000000000000000000000001",
  "balanceAccountId": "BA000000000000000000001",
  "transferInstrumentId": "SE00000000000000000000001",
  "currency": "EUR",
  "reference": "Monthly payout",
  "description": "Scheduled payout to merchant bank account",
  "referenceForBeneficiary": "PAYOUT-REF-001",
  "retainedAmount": 10000,
  "minPayoutAmount": 1000,
  "maxPayoutAmount": 100000000,
  "createdAt": "2024-01-15T10:30:00Z",
  "enabled": true,
  "frequency": "monthly",
  "frequencyValue": 1
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the resource was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Balance Accounts-Balance Account Id-Payout Schedules-Id

Delete a payout schedule applied to a balance account.

:information_source: **Note** This endpoint does not require authentication.

```php
function deleteBalanceAccountsBalanceAccountIdPayoutSchedulesId(string $balanceAccountId, string $id): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `id` | `string` | Template, Required | The unique identifier of the payout schedule applied to the balance account. |

## Response Type

**204**: OK - The request has succeeded.

`void`

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$id = 'id0';

$managedPayoutSchedulesApi = $client->getManagedPayoutSchedulesApi();

try {
    $managedPayoutSchedulesApi->deleteBalanceAccountsBalanceAccountIdPayoutSchedulesId(
        $balanceAccountId,
        $id
    );
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the resource was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Patch-Balance Accounts-Balance Account Id-Payout Schedules-Id

Update a managed payout schedule applied to a balance account. If an optional parameter is not included in the request, it remains unchanged.

:information_source: **Note** This endpoint does not require authentication.

```php
function patchBalanceAccountsBalanceAccountIdPayoutSchedulesId(
    string $balanceAccountId,
    string $id,
    BalanceAccountConfigurationUpdate $body
): BalanceAccountConfiguration
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `id` | `string` | Template, Required | The unique identifier of the payout schedule applied to the balance account. |
| `body` | [`BalanceAccountConfigurationUpdate`](../../doc/models/balance-account-configuration-update.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`BalanceAccountConfiguration`](../../doc/models/balance-account-configuration.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$id = 'id0';

$body = BalanceAccountConfigurationUpdateBuilder::init()
    ->description('Updated payout description')
    ->enabled(false)
    ->retainedAmount(20000)
    ->build();

$managedPayoutSchedulesApi = $client->getManagedPayoutSchedulesApi();

try {
    $result = $managedPayoutSchedulesApi->patchBalanceAccountsBalanceAccountIdPayoutSchedulesId(
        $balanceAccountId,
        $id,
        $body
    );
    echo 'BalanceAccountConfiguration:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "PSAC00000000000000000000000001",
  "balancePlatformPayoutScheduleId": "PSPC00000000000000000000000001",
  "balanceAccountId": "BA000000000000000000001",
  "transferInstrumentId": "SE00000000000000000000001",
  "currency": "EUR",
  "reference": "Monthly payout",
  "description": "Updated payout description",
  "referenceForBeneficiary": "PAYOUT-REF-001",
  "retainedAmount": 20000,
  "minPayoutAmount": 1000,
  "maxPayoutAmount": 100000000,
  "createdAt": "2024-01-15T10:30:00Z",
  "updatedAt": "2024-01-16T14:00:00Z",
  "enabled": false,
  "frequency": "monthly",
  "frequencyValue": 1
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the resource was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Balance Accounts-Balance Account Id-Payout Schedules-Id-Executions

View information about the executions of a managed payout schedule on the specified balance account. An execution is an attempt to make a payout according to the payout schedule.

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalanceAccountsBalanceAccountIdPayoutSchedulesIdExecutions(
    string $balanceAccountId,
    string $id,
    int $offset,
    ?array $results = null,
    ?int $limit = null
): PayoutScheduleExecutions
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `id` | `string` | Template, Required | The unique identifier of the payout schedule on the balance account. |
| `offset` | `int` | Query, Required | The page number to be returned.<br><br>Default: **1**<br><br>**Constraints**: `>= 1`, `<= 100` |
| `results` | [`?(string(ExecutionResultEnum)[])`](../../doc/models/execution-result-enum.md) | Query, Optional | Contains a list of payout statuses. If included, the response returns only executed payouts that currently have one of the specified statuses.<br><br>Possible statuses:<br><br>- **succeeded**: The payout was sent successfully.<br>- **failed**: The payout was not sent due to an error.<br>- **skipped**: The payout was not triggered as expected. |
| `limit` | `?int` | Query, Optional | The number of items returned per page.<br><br>Default: **10**<br><br>**Constraints**: `>= 10` |

## Response Type

**200**: OK - The request has succeeded.

[`PayoutScheduleExecutions`](../../doc/models/payout-schedule-executions.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$id = 'id0';

$offset = 12;

$managedPayoutSchedulesApi = $client->getManagedPayoutSchedulesApi();

try {
    $result = $managedPayoutSchedulesApi->getBalanceAccountsBalanceAccountIdPayoutSchedulesIdExecutions(
        $balanceAccountId,
        $id,
        $offset
    );
    echo 'PayoutScheduleExecutions:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "payoutScheduleExecutions": [
    {
      "id": "PS0000000000001",
      "result": "skipped",
      "triggeredAt": "2026-03-11T08:00:00Z",
      "resultDetails": {
        "reasonCode": "noBalanceToPayOut",
        "reason": "No balance to pay out"
      }
    },
    {
      "id": "PS0000000000002",
      "result": "succeeded",
      "triggeredAt": "2026-03-12T08:00:00Z",
      "resultDetails": {
        "transferId": "A0A0A0A0A0A0A0A0"
      }
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the resource was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Balance Platforms-Balance Platform Id-Payout Schedules

Returns a list of all the payout schedules that are configured for your balance platform. You can use query parameters to filter the elements that are returned in the list.

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalancePlatformsBalancePlatformIdPayoutSchedules(
    string $balancePlatformId,
    ?string $countryCode = null,
    ?string $currency = null
): BalancePlatformConfigurations
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balancePlatformId` | `string` | Template, Required | The unique identifier of the balance platform. |
| `countryCode` | `?string` | Query, Optional | The two-letter [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code of the country to which the payout configuration applies. |
| `currency` | `?string` | Query, Optional | The three-character [ISO currency code](https://docs.adyen.com/development-resources/currency-codes) of the currency used in the payout configuration. |

## Response Type

**200**: OK - The request has succeeded.

[`BalancePlatformConfigurations`](../../doc/models/balance-platform-configurations.md)

## Example Usage

```php
$balancePlatformId = 'balancePlatformId8';

$managedPayoutSchedulesApi = $client->getManagedPayoutSchedulesApi();

try {
    $result = $managedPayoutSchedulesApi->getBalancePlatformsBalancePlatformIdPayoutSchedules($balancePlatformId);
    echo 'BalancePlatformConfigurations:';
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
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the resource was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Balance Platforms-Balance Platform Id-Payout Schedules-Id

Returns the specified managed payout schedule configured on your balance platform.

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalancePlatformsBalancePlatformIdPayoutSchedulesId(
    string $balancePlatformId,
    string $id
): BalancePlatformConfiguration
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balancePlatformId` | `string` | Template, Required | The unique identifier of the balance platform. |
| `id` | `string` | Template, Required | The unique identifier of the payout configuration for your balance platform. |

## Response Type

**200**: OK - The request has succeeded.

[`BalancePlatformConfiguration`](../../doc/models/balance-platform-configuration.md)

## Example Usage

```php
$balancePlatformId = 'balancePlatformId8';

$id = 'id0';

$managedPayoutSchedulesApi = $client->getManagedPayoutSchedulesApi();

try {
    $result = $managedPayoutSchedulesApi->getBalancePlatformsBalancePlatformIdPayoutSchedulesId(
        $balancePlatformId,
        $id
    );
    echo 'BalancePlatformConfiguration:';
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
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the resource was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

