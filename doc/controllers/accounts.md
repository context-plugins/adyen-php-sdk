# Accounts

```php
$accountsApi = $client->getAccountsApi();
```

## Class Name

`AccountsApi`

## Methods

* [Post-Close Account](../../doc/controllers/accounts.md#post-close-account)
* [Post-Create Account](../../doc/controllers/accounts.md#post-create-account)
* [Post-Update Account](../../doc/controllers/accounts.md#post-update-account)


# Post-Close Account

Closes an account. If an account is closed, you cannot process transactions, pay out its funds, or reopen it. If payments are made to a closed account, the payments are sent to your liable account.

```php
function postCloseAccount(?CloseAccountRequest $body = null): CloseAccountResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CloseAccountRequest`](../../doc/models/close-account-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CloseAccountResponse`](../../doc/models/close-account-response.md)

## Example Usage

```php
$body = CloseAccountRequestBuilder::init(
    'CODE_OF_ACCOUNT'
)->build();

$accountsApi = $client->getAccountsApi();

try {
    $result = $accountsApi->postCloseAccount($body);
    echo 'CloseAccountResponse:';
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


# Post-Create Account

Creates an account under an account holder. An account holder can have [multiple accounts](https://docs.adyen.com/classic-platforms/account-holders-and-accounts#create-additional-accounts).

```php
function postCreateAccount(?CreateAccountRequest $body = null): CreateAccountResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CreateAccountRequest`](../../doc/models/create-account-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CreateAccountResponse`](../../doc/models/create-account-response.md)

## Example Usage

```php
$body = CreateAccountRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER'
)->build();

$accountsApi = $client->getAccountsApi();

try {
    $result = $accountsApi->postCreateAccount($body);
    echo 'CreateAccountResponse:';
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


# Post-Update Account

Updates the description or payout schedule of an account.

```php
function postUpdateAccount(?UpdateAccountRequest $body = null): UpdateAccountResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?UpdateAccountRequest`](../../doc/models/update-account-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`UpdateAccountResponse`](../../doc/models/update-account-response.md)

## Example Usage

```php
$body = UpdateAccountRequestBuilder::init(
    'CODE_OF_ACCOUNT'
)
    ->payoutSchedule(
        UpdatePayoutScheduleRequest2Builder::init(
            Schedule1Enum::WEEKLY
        )
            ->action(ActionEnum::CLOSE)
            ->build()
    )
    ->build();

$accountsApi = $client->getAccountsApi();

try {
    $result = $accountsApi->postUpdateAccount($body);
    echo 'UpdateAccountResponse:';
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

