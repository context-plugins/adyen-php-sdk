# Recurringtopups

```php
$recurringtopupsApi = $client->getRecurringtopupsApi();
```

## Class Name

`RecurringtopupsApi`

## Methods

* [Get-Balance Accounts-Balance Account Id-Recurring Top Ups](../../doc/controllers/recurringtopups.md#get-balance-accounts-balance-account-id-recurring-top-ups)
* [Post-Balance Accounts-Balance Account Id-Recurring Top Ups](../../doc/controllers/recurringtopups.md#post-balance-accounts-balance-account-id-recurring-top-ups)
* [Delete-Balance Accounts-Balance Account Id-Recurring Top Ups-Top Up Id](../../doc/controllers/recurringtopups.md#delete-balance-accounts-balance-account-id-recurring-top-ups-top-up-id)
* [Patch-Balance Accounts-Balance Account Id-Recurring Top Ups-Top Up Id](../../doc/controllers/recurringtopups.md#patch-balance-accounts-balance-account-id-recurring-top-ups-top-up-id)


# Get-Balance Accounts-Balance Account Id-Recurring Top Ups

View all recurring top ups configured for a specific `balanceAccountId`.

For more information, refer to [Manage recurring top-ups](https://docs.adyen.com/issuing/add-manage-funds/top-ups/manage-recurring-top-ups).

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalanceAccountsBalanceAccountIdRecurringTopUps(
    string $balanceAccountId,
    ?int $limit = 10,
    ?string $cursor = null
): RecurringTopUpsResult
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `limit` | `?int` | Query, Optional | The number of items to return per page. Value must be between 1 and 100.<br><br>**Default**: `10`<br><br>**Constraints**: `>= 1`, `<= 100` |
| `cursor` | `?string` | Query, Optional | The cursor used for pagination. Required if you want to see the next or previous page of results. |

## Response Type

**200**: OK - the request has succeeded.

[`RecurringTopUpsResult`](../../doc/models/recurring-top-ups-result.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$limit = 10;

$recurringTopUpsApi = $client->getRecurringTopUpsApi();

try {
    $result = $recurringTopUpsApi->getBalanceAccountsBalanceAccountIdRecurringTopUps(
        $balanceAccountId,
        $limit
    );
    echo 'RecurringTopUpsResult:';
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
  "recurringTopUps": [
    {
      "id": "TUPC0000000000000000000001",
      "counterparty": {
        "transferInstrumentId": "SE000000000000000000000001"
      },
      "description": "My description",
      "topUpAmount": {
        "fixed": {
          "value": 1000,
          "currency": "EUR"
        }
      },
      "trigger": {
        "schedule": {
          "type": "weekdays"
        },
        "threshold": {
          "value": 100,
          "currency": "EUR"
        }
      },
      "status": "active"
    }
  ],
  "link": {
    "next": {
      "href": "/balanceAccounts/balanceAccount1/recurringTopUps?limit=10&cursor=nextCursorToken"
    },
    "previous": {
      "href": "/balanceAccounts/balanceAccount1/recurringTopUps?limit=10&cursor=previousCursorToken"
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the recurring top up was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Balance Accounts-Balance Account Id-Recurring Top Ups

Create a recurring top up configuration.

For more information, refer to [Create recurring top-ups](https://docs.adyen.com/issuing/add-manage-funds/top-ups/create-recurring-top-ups).

:information_source: **Note** This endpoint does not require authentication.

```php
function postBalanceAccountsBalanceAccountIdRecurringTopUps(
    string $balanceAccountId,
    CreateRecurringTopUp $body
): RecurringTopUp
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `body` | [`CreateRecurringTopUp`](../../doc/models/create-recurring-top-up.md) | Body, Required | - |

## Response Type

**200**: OK - the request has succeeded.

[`RecurringTopUp`](../../doc/models/recurring-top-up.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$body = CreateRecurringTopUpBuilder::init(
    TopUpCounterparty1Builder::init(
        'SE000000000000000000000001'
    )->build(),
    'My description',
    TopUpAmount1Builder::init()
        ->fixed(
            Amount17Builder::init(
                'EUR',
                1000
            )->build()
        )->build(),
    Trigger1Builder::init(
        Amount17Builder::init(
            'EUR',
            100
        )->build()
    )
        ->schedule(
            Schedule21Builder::init(
                ScheduleType1Enum::WEEKDAYS
            )->build()
        )->build()
)->build();

$recurringTopUpsApi = $client->getRecurringTopUpsApi();

try {
    $result = $recurringTopUpsApi->postBalanceAccountsBalanceAccountIdRecurringTopUps(
        $balanceAccountId,
        $body
    );
    echo 'RecurringTopUp:';
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
  "id": "TUPC0000000000000000000001",
  "counterparty": {
    "transferInstrumentId": "SE000000000000000000000001"
  },
  "description": "My description",
  "topUpAmount": {
    "fixed": {
      "value": 1000,
      "currency": "EUR"
    }
  },
  "trigger": {
    "schedule": {
      "type": "weekdays"
    },
    "threshold": {
      "value": 100,
      "currency": "EUR"
    }
  },
  "status": "active"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Balance Accounts-Balance Account Id-Recurring Top Ups-Top Up Id

Delete a recurring top up configuration by `topUpId`.

For more information, refer to [Manage recurring top-ups](https://docs.adyen.com/issuing/add-manage-funds/top-ups/manage-recurring-top-ups).

:information_source: **Note** This endpoint does not require authentication.

```php
function deleteBalanceAccountsBalanceAccountIdRecurringTopUpsTopUpId(string $balanceAccountId, string $topUpId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `topUpId` | `string` | Template, Required | The unique identifier of the recurring top-up you want to delete. |

## Response Type

**204**: No Content - the request has been successfully processed, but there is no additional content.

`mixed`

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$topUpId = 'topUpId8';

$recurringTopUpsApi = $client->getRecurringTopUpsApi();

try {
    $result = $recurringTopUpsApi->deleteBalanceAccountsBalanceAccountIdRecurringTopUpsTopUpId(
        $balanceAccountId,
        $topUpId
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
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the recurring top up was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Patch-Balance Accounts-Balance Account Id-Recurring Top Ups-Top Up Id

Update the configuration of an existing recurring top up.

For more information, refer to [Manage recurring top-ups](https://docs.adyen.com/issuing/add-manage-funds/top-ups/manage-recurring-top-ups).

:information_source: **Note** This endpoint does not require authentication.

```php
function patchBalanceAccountsBalanceAccountIdRecurringTopUpsTopUpId(
    string $balanceAccountId,
    string $topUpId,
    PatchableCreateRecurringTopUp $body
): RecurringTopUp
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `string` | Template, Required | The unique identifier of the balance account. |
| `topUpId` | `string` | Template, Required | The unique identifier of the recurring top-up you want to update. |
| `body` | [`PatchableCreateRecurringTopUp`](../../doc/models/patchable-create-recurring-top-up.md) | Body, Required | - |

## Response Type

**200**: OK - the request has succeeded.

[`RecurringTopUp`](../../doc/models/recurring-top-up.md)

## Example Usage

```php
$balanceAccountId = 'balanceAccountId8';

$topUpId = 'topUpId8';

$body = PatchableCreateRecurringTopUpBuilder::init()
    ->description('new description')
    ->build();

$recurringTopUpsApi = $client->getRecurringTopUpsApi();

try {
    $result = $recurringTopUpsApi->patchBalanceAccountsBalanceAccountIdRecurringTopUpsTopUpId(
        $balanceAccountId,
        $topUpId,
        $body
    );
    echo 'RecurringTopUp:';
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
  "id": "TUPC0000000000000000000001",
  "counterparty": {
    "transferInstrumentId": "SE000000000000000000000001"
  },
  "description": "new description",
  "topUpAmount": {
    "fixed": {
      "value": 1000,
      "currency": "EUR"
    }
  },
  "trigger": {
    "schedule": {
      "type": "weekdays"
    },
    "threshold": {
      "value": 100,
      "currency": "EUR"
    }
  },
  "status": "inactive"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

