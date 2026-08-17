# Grantaccounts

```php
$grantaccountsApi = $client->getGrantaccountsApi();
```

## Class Name

`GrantaccountsApi`

## Methods

* [Get-Grant Accounts-Id](../../doc/controllers/grantaccounts.md#get-grant-accounts-id)
* [Get-Grant Accounts-Id 1](../../doc/controllers/grantaccounts.md#get-grant-accounts-id-1)


# Get-Grant Accounts-Id

**This endpoint is deprecated.**

Returns the details of the [grant account](https://docs.adyen.com/platforms/capital#grant-account).

```php
function getGrantAccountsId(string $id): CapitalGrantAccount
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the grant account. |

## Response Type

**200**: OK - the request has succeeded.

[`CapitalGrantAccount`](../../doc/models/capital-grant-account.md)

## Example Usage

```php
$id = 'id0';

$grantAccountsApi = $client->getGrantAccountsApi();

try {
    $result = $grantAccountsApi->getGrantAccountsId($id);
    echo 'CapitalGrantAccount:';
    var_dump($result);
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


# Get-Grant Accounts-Id 1

Returns the details of the specified grant account. This account tracks existing grants in your marketplace or platform.

:information_source: **Note** This endpoint does not require authentication.

```php
function getGrantAccountsId1(string $id): GrantAccount
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the grant account. |

## Response Type

**200**: OK - The request has succeeded.

[`GrantAccount`](../../doc/models/grant-account.md)

## Example Usage

```php
$id = 'id0';

$grantAccountsApi = $client->getGrantAccountsApi();

try {
    $result = $grantAccountsApi->getGrantAccountsId1($id);
    echo 'GrantAccount:';
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
| 404 | Not Found - The entity was not found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

