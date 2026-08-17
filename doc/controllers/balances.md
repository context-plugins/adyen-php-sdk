# Balances

```php
$balancesApi = $client->getBalancesApi();
```

## Class Name

`BalancesApi`

## Methods

* [Get-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings](../../doc/controllers/balances.md#get-balance-platforms-balance-platform-id-webhooks-webhook-id-settings)
* [Post-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings](../../doc/controllers/balances.md#post-balance-platforms-balance-platform-id-webhooks-webhook-id-settings)
* [Get-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings-Setting Id](../../doc/controllers/balances.md#get-balance-platforms-balance-platform-id-webhooks-webhook-id-settings-setting-id)
* [Delete-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings-Setting Id](../../doc/controllers/balances.md#delete-balance-platforms-balance-platform-id-webhooks-webhook-id-settings-setting-id)
* [Patch-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings-Setting Id](../../doc/controllers/balances.md#patch-balance-platforms-balance-platform-id-webhooks-webhook-id-settings-setting-id)


# Get-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings

Returns all balance webhook settings configured for triggering [balance webhooks](https://docs.adyen.com/api-explorer/balance-webhooks/latest/post/balanceAccount.balance.updated).

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettings(
    string $balancePlatformId,
    string $webhookId
): WebhookSettings
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balancePlatformId` | `string` | Template, Required | The unique identifier of the balance platform. |
| `webhookId` | `string` | Template, Required | The unique identifier of the balance webhook. |

## Response Type

**200**: OK - the request has succeeded.

[`WebhookSettings`](../../doc/models/webhook-settings.md)

## Example Usage

```php
$balancePlatformId = 'balancePlatformId8';

$webhookId = 'webhookId6';

$balancesApi = $client->getBalancesApi();

try {
    $result = $balancesApi->getBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettings(
        $balancePlatformId,
        $webhookId
    );
    echo 'WebhookSettings:';
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
  "webhookSettings": [
    {
      "id": "BWHS00000000000000000000000001",
      "type": "balance",
      "target": {
        "type": "balancePlatform",
        "id": "YOUR_BALANCE_PLATFORM"
      },
      "currency": "USD",
      "status": "active",
      "conditions": [
        {
          "balanceType": "available",
          "conditionType": "lessThan",
          "value": 500000
        }
      ]
    },
    {
      "id": "BWHS00000000000000000000000002",
      "type": "balance",
      "target": {
        "type": "balanceAccount",
        "id": "BA00000000000000000LIABLE"
      },
      "currency": "USD",
      "status": "active",
      "conditions": [
        {
          "balanceType": "available",
          "conditionType": "greaterThan",
          "value": 1000000
        }
      ]
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the payment was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings

Configures the criteria for triggering [balance webhooks](https://docs.adyen.com/api-explorer/balance-webhooks/1/post/balancePlatform.balanceAccount.balance.updated).

Adyen sends balance webhooks to notify you of balance changes in your balance platform. They can be triggered when the balance reaches, exceeds, or drops below a specific value in a specific currency.

You can get notified about balance changes in your entire balance platform, in the balance accounts of a specific user, or a specific balance account. The hierarchy between the webhook settings are based on the following business logic:

* Settings on a higher level apply to all lower level resources (balance platform > account holder > balance acocunt).

* The most granular setting overrides higher level settings (balance account > account holder > balance platform).

:information_source: **Note** This endpoint does not require authentication.

```php
function postBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettings(
    string $balancePlatformId,
    string $webhookId,
    BalanceWebhookSettingInfo $body
): WebhookSetting
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balancePlatformId` | `string` | Template, Required | The unique identifier of the balance platform. |
| `webhookId` | `string` | Template, Required | The unique identifier of the balance webhook. |
| `body` | [`BalanceWebhookSettingInfo`](../../doc/models/balance-webhook-setting-info.md) | Body, Required | - |

## Response Type

**200**: OK - the request has succeeded.

[`WebhookSetting`](../../doc/models/webhook-setting.md)

## Example Usage

```php
$balancePlatformId = 'balancePlatformId8';

$webhookId = 'webhookId6';

$body = BalanceWebhookSettingInfoBuilder::init(
    'USD',
    Status6Enum::ACTIVE,
    Target1Builder::init(
        'BA00000000000000000LIABLE',
        Type181Enum::BALANCEACCOUNT
    )->build()
)
    ->conditions(
        [
            ConditionBuilder::init(
                BalanceTypeEnum::AVAILABLE,
                ConditionTypeEnum::LESSTHAN,
                500000
            )->build()
        ]
    )->build();

$balancesApi = $client->getBalancesApi();

try {
    $result = $balancesApi->postBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettings(
        $balancePlatformId,
        $webhookId,
        $body
    );
    echo 'WebhookSetting:';
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
  "id": "BWHS00000000000000000000000001",
  "type": "balance",
  "target": {
    "type": "balanceAccount",
    "id": "BA00000000000000000LIABLE"
  },
  "currency": "USD",
  "status": "active",
  "conditions": [
    {
      "balanceType": "available",
      "conditionType": "lessThan",
      "value": 500000
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the payment was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings-Setting Id

Returns the details of a specific balance webhook setting configured for triggering [balance webhooks](https://docs.adyen.com/api-explorer/balance-webhooks/latest/post/balanceAccount.balance.updated).

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettingsSettingId(
    string $balancePlatformId,
    string $webhookId,
    string $settingId
): WebhookSetting
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balancePlatformId` | `string` | Template, Required | The unique identifier of the balance platform. |
| `webhookId` | `string` | Template, Required | The unique identifier of the balance webhook. |
| `settingId` | `string` | Template, Required | The unique identifier of the balance webhook setting. |

## Response Type

**200**: OK - the request has succeeded.

[`WebhookSetting`](../../doc/models/webhook-setting.md)

## Example Usage

```php
$balancePlatformId = 'balancePlatformId8';

$webhookId = 'webhookId6';

$settingId = 'settingId0';

$balancesApi = $client->getBalancesApi();

try {
    $result = $balancesApi->getBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettingsSettingId(
        $balancePlatformId,
        $webhookId,
        $settingId
    );
    echo 'WebhookSetting:';
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
  "id": "BWHS00000000000000000000000001",
  "type": "balance",
  "target": {
    "type": "balancePlatform",
    "id": "YOUR_BALANCE_PLATFORM"
  },
  "currency": "USD",
  "status": "active",
  "conditions": [
    {
      "balanceType": "available",
      "conditionType": "lessThan",
      "value": 500000
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the payment was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings-Setting Id

Deletes a balance webhook setting that contains the conditions for triggering [balance webhooks](https://docs.adyen.com/api-explorer/balance-webhooks/latest/post/balanceAccount.balance.updated).

:information_source: **Note** This endpoint does not require authentication.

```php
function deleteBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettingsSettingId(
    string $balancePlatformId,
    string $webhookId,
    string $settingId
)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balancePlatformId` | `string` | Template, Required | The unique identifier of the balance platform. |
| `webhookId` | `string` | Template, Required | The unique identifier of the balance webhook. |
| `settingId` | `string` | Template, Required | The unique identifier of the balance webhook setting. |

## Response Type

**204**: No Content - the request has been successfully processed, but there is no additional content.

`mixed`

## Example Usage

```php
$balancePlatformId = 'balancePlatformId8';

$webhookId = 'webhookId6';

$settingId = 'settingId0';

$balancesApi = $client->getBalancesApi();

try {
    $result = $balancesApi->deleteBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettingsSettingId(
        $balancePlatformId,
        $webhookId,
        $settingId
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
| 404 | Not Found - the payment was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Patch-Balance Platforms-Balance Platform Id-Webhooks-Webhook Id-Settings-Setting Id

Updates the conditions the balance change needs to meet for Adyen to send a [balance webhook](https://docs.adyen.com/api-explorer/balance-webhooks/latest/post/balanceAccount.balance.updated).

:information_source: **Note** This endpoint does not require authentication.

```php
function patchBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettingsSettingId(
    string $balancePlatformId,
    string $webhookId,
    string $settingId,
    BalanceWebhookSettingInfoUpdate $body
): WebhookSetting
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balancePlatformId` | `string` | Template, Required | The unique identifier of the balance platform. |
| `webhookId` | `string` | Template, Required | The unique identifier of the balance webhook. |
| `settingId` | `string` | Template, Required | The unique identifier of the balance webhook setting. |
| `body` | [`BalanceWebhookSettingInfoUpdate`](../../doc/models/balance-webhook-setting-info-update.md) | Body, Required | - |

## Response Type

**200**: OK - the request has succeeded.

[`WebhookSetting`](../../doc/models/webhook-setting.md)

## Example Usage

```php
$balancePlatformId = 'balancePlatformId8';

$webhookId = 'webhookId6';

$settingId = 'settingId0';

$body = BalanceWebhookSettingInfoUpdateBuilder::init()
    ->status(Status6Enum::INACTIVE)
    ->type(Type201Enum::BALANCE)
    ->build();

$balancesApi = $client->getBalancesApi();

try {
    $result = $balancesApi->patchBalancePlatformsBalancePlatformIdWebhooksWebhookIdSettingsSettingId(
        $balancePlatformId,
        $webhookId,
        $settingId,
        $body
    );
    echo 'WebhookSetting:';
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
  "type": "balance",
  "id": "BWHS00000000000000000000000001",
  "target": {
    "type": "balanceAccount",
    "id": "BA00000000000000000LIABLE"
  },
  "currency": "USD",
  "status": "inactive",
  "conditions": [
    {
      "balanceType": "available",
      "conditionType": "lessThan",
      "value": 500000
    },
    {
      "balanceType": "balance",
      "conditionType": "greaterThan",
      "value": 1000000
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - the payment was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

