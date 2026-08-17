# Transferlimits-Balanceplatformlevel

```php
$transferlimitsBalanceplatformlevelApi = $client->getTransferlimitsBalanceplatformlevelApi();
```

## Class Name

`TransferlimitsBalanceplatformlevelApi`

## Methods

* [Get-Balance Platforms-Id-Transfer Limits](../../doc/controllers/transferlimits-balanceplatformlevel.md#get-balance-platforms-id-transfer-limits)
* [Post-Balance Platforms-Id-Transfer Limits](../../doc/controllers/transferlimits-balanceplatformlevel.md#post-balance-platforms-id-transfer-limits)
* [Get-Balance Platforms-Id-Transfer Limits-Transfer Limit Id](../../doc/controllers/transferlimits-balanceplatformlevel.md#get-balance-platforms-id-transfer-limits-transfer-limit-id)
* [Delete-Balance Platforms-Id-Transfer Limits-Transfer Limit Id](../../doc/controllers/transferlimits-balanceplatformlevel.md#delete-balance-platforms-id-transfer-limits-transfer-limit-id)


# Get-Balance Platforms-Id-Transfer Limits

Filter and view the transfer limits configured for your balance platform using the balance platform's unique `id` and the available query parameters.

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalancePlatformsIdTransferLimits(
    string $id,
    ?string $scope = null,
    ?string $transferType = null,
    ?string $status = null
): TransferLimitListResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the balance platform. |
| `scope` | [`?string(ScopeEnum)`](../../doc/models/scope-enum.md) | Query, Optional | The scope to which the transfer limit applies. Possible values:<br><br>* **perTransaction**: you set a maximum amount for each transfer made from the balance account or balance platform.<br>* **perDay**: you set a maximum total amount for all transfers made from the balance account or balance platform in a day. |
| `transferType` | [`?string(TransferTypeEnum)`](../../doc/models/transfer-type-enum.md) | Query, Optional | The type of transfer to which the limit applies. Possible values:<br><br>* **instant**: the limit applies to transfers with an **instant** priority.<br>* **all**: the limit applies to all transfers, regardless of priority. |
| `status` | [`?string(LimitStatusEnum)`](../../doc/models/limit-status-enum.md) | Query, Optional | The status of the transfer limit. Possible values:<br><br>* **active**: the limit is currently active.<br>* **inactive**: the limit is currently inactive.<br>* **pendingSCA**: the limit is pending until your user performs SCA.<br>* **scheduled**: the limit is scheduled to become active at a future date. |

## Response Type

**200**: OK - The request has succeeded.

[`TransferLimitListResponse`](../../doc/models/transfer-limit-list-response.md)

## Example Usage

```php
$id = 'id0';

$transferLimitsBalancePlatformLevelApi = $client->getTransferLimitsBalancePlatformLevelApi();

try {
    $result = $transferLimitsBalancePlatformLevelApi->getBalancePlatformsIdTransferLimits($id);
    echo 'TransferLimitListResponse:';
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
  "transferLimits": [
    {
      "amount": {
        "currency": "EUR",
        "value": 10000
      },
      "endsAt": "2026-08-13T23:00:00+01:00",
      "id": "TRLI00000000000000000000000001",
      "limitStatus": "active",
      "reference": "Your reference for the transfer limit",
      "scaInformation": {
        "exemption": "initialLimit",
        "status": "notPerformed"
      },
      "scope": "perTransaction",
      "startsAt": "2025-08-13T23:00:00+01:00",
      "transferType": "instant"
    },
    {
      "amount": {
        "currency": "EUR",
        "value": 20000
      },
      "endsAt": "2026-08-13T23:00:00+01:00",
      "id": "TRLI00000000000000000000000002",
      "limitStatus": "active",
      "reference": "Your reference for the transfer limit",
      "scaInformation": {
        "exemption": "initialLimit",
        "status": "notPerformed"
      },
      "scope": "perTransaction",
      "startsAt": "2025-08-13T23:00:00+01:00",
      "transferType": "all"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Not found - One of the transfer limits could not be found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Content - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Balance Platforms-Id-Transfer Limits

Create a transfer limit for your balance platform using the unique `id` of your balance platform.

:information_source: **Note** This endpoint does not require authentication.

```php
function postBalancePlatformsIdTransferLimits(string $id, CreateTransferLimitRequest $body): TransferLimit
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the balance platform. |
| `body` | [`CreateTransferLimitRequest`](../../doc/models/create-transfer-limit-request.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`TransferLimit`](../../doc/models/transfer-limit.md)

## Example Usage

```php
$id = 'id0';

$body = CreateTransferLimitRequestBuilder::init(
    Amount17Builder::init(
        'EUR',
        10000
    )->build(),
    ScopeEnum::PERTRANSACTION,
    TransferTypeEnum::ALL
)
    ->endsAt(DateTimeHelper::fromRfc3339DateTime('2026-08-14T00:00:00+01:00'))
    ->reference('Your reference for the transfer limit')
    ->scaInformation(
        CreateScaInformation1Builder::init()
            ->scaOnApproval(true)
            ->build()
    )
    ->startsAt(DateTimeHelper::fromRfc3339DateTime('2025-08-15T06:36:20+01:00'))
    ->build();

$transferLimitsBalancePlatformLevelApi = $client->getTransferLimitsBalancePlatformLevelApi();

try {
    $result = $transferLimitsBalancePlatformLevelApi->postBalancePlatformsIdTransferLimits(
        $id,
        $body
    );
    echo 'TransferLimit:';
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
  "amount": {
    "currency": "EUR",
    "value": 10000
  },
  "endsAt": "2026-08-13T23:00:00+01:00",
  "id": "TRLI00000000000000000000000001",
  "limitStatus": "pendingSCA",
  "reference": "Your reference for the transfer limit",
  "scaInformation": {
    "status": "pending"
  },
  "scope": "perTransaction",
  "startsAt": "2025-08-15T06:36:20+01:00",
  "transferType": "all"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Not found - One of the transfer limits could not be found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Content - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Balance Platforms-Id-Transfer Limits-Transfer Limit Id

Get the details of a transfer limit using its unique `transferLimitId`.

:information_source: **Note** This endpoint does not require authentication.

```php
function getBalancePlatformsIdTransferLimitsTransferLimitId(string $id, string $transferLimitId): TransferLimit
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the balance platform. |
| `transferLimitId` | `string` | Template, Required | The unique identifier of the transfer limit. |

## Response Type

**200**: OK - The request has succeeded.

[`TransferLimit`](../../doc/models/transfer-limit.md)

## Example Usage

```php
$id = 'id0';

$transferLimitId = 'transferLimitId6';

$transferLimitsBalancePlatformLevelApi = $client->getTransferLimitsBalancePlatformLevelApi();

try {
    $result = $transferLimitsBalancePlatformLevelApi->getBalancePlatformsIdTransferLimitsTransferLimitId(
        $id,
        $transferLimitId
    );
    echo 'TransferLimit:';
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
  "amount": {
    "currency": "EUR",
    "value": 10000
  },
  "endsAt": "2026-08-13T23:00:00+01:00",
  "id": "TRLI00000000000000000000000001",
  "limitStatus": "active",
  "reference": "Your reference for the transfer limit",
  "scaInformation": {
    "exemption": "initialLimit",
    "status": "notPerformed"
  },
  "scope": "perTransaction",
  "startsAt": "2025-08-13T23:00:00+01:00",
  "transferType": "all"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Not found - One of the transfer limits could not be found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Content - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Balance Platforms-Id-Transfer Limits-Transfer Limit Id

Delete a scheduled or pending transfer limit using its unique `transferLimitId`. You cannot delete an active limit.

:information_source: **Note** This endpoint does not require authentication.

```php
function deleteBalancePlatformsIdTransferLimitsTransferLimitId(string $id, string $transferLimitId): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the balance platform. |
| `transferLimitId` | `string` | Template, Required | The unique identifier of the transfer limit. |

## Response Type

**204**: No Content - The request has succeeded.

`void`

## Example Usage

```php
$id = 'id0';

$transferLimitId = 'transferLimitId6';

$transferLimitsBalancePlatformLevelApi = $client->getTransferLimitsBalancePlatformLevelApi();

try {
    $transferLimitsBalancePlatformLevelApi->deleteBalancePlatformsIdTransferLimitsTransferLimitId(
        $id,
        $transferLimitId
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
| 404 | Not found - One of the transfer limits could not be found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Content - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

