# Users-Companylevel

```php
$usersCompanylevelApi = $client->getUsersCompanylevelApi();
```

## Class Name

`UsersCompanylevelApi`

## Methods

* [Get-Companies-Company Id-Users](../../doc/controllers/users-companylevel.md#get-companies-company-id-users)
* [Post-Companies-Company Id-Users](../../doc/controllers/users-companylevel.md#post-companies-company-id-users)
* [Get-Companies-Company Id-Users-User Id](../../doc/controllers/users-companylevel.md#get-companies-company-id-users-user-id)
* [Patch-Companies-Company Id-Users-User Id](../../doc/controllers/users-companylevel.md#patch-companies-company-id-users-user-id)


# Get-Companies-Company Id-Users

Returns the list of users for the `companyId` identified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Users read and write

```php
function getCompaniesCompanyIdUsers(
    string $companyId,
    ?int $pageNumber = null,
    ?int $pageSize = null,
    ?string $username = null
): ListCompanyUsersResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `pageNumber` | `?int` | Query, Optional | The number of the page to return. |
| `pageSize` | `?int` | Query, Optional | The number of items to have on a page. Maximum value is **100**. The default is **10** items on a page. |
| `username` | `?string` | Query, Optional | The partial or complete username to select all users that match. |

## Response Type

**200**: OK - the request has succeeded.

[`ListCompanyUsersResponse`](../../doc/models/list-company-users-response.md)

## Example Usage

```php
$companyId = 'companyId0';

$usersCompanyLevelApi = $client->getUsersCompanyLevelApi();

try {
    $result = $usersCompanyLevelApi->getCompaniesCompanyIdUsers($companyId);
    echo 'ListCompanyUsersResponse:';
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


# Post-Companies-Company Id-Users

Creates the user for the `companyId` identified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Users read and write

```php
function postCompaniesCompanyIdUsers(
    string $companyId,
    ?CreateCompanyUserRequest $body = null
): CreateCompanyUserResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `body` | [`?CreateCompanyUserRequest`](../../doc/models/create-company-user-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CreateCompanyUserResponse`](../../doc/models/create-company-user-response.md)

## Example Usage

```php
$companyId = 'companyId0';

$body = CreateCompanyUserRequestBuilder::init(
    'john.smith@example.com',
    NameBuilder::init(
        'John',
        'Smith'
    )->build(),
    'johnsmith'
)
    ->associatedMerchantAccounts(
        [
            'YOUR_MERCHANT_ACCOUNT'
        ]
    )
    ->loginMethod('Email')
    ->roles(
        [
            'Merchant standard role',
            'Merchant admin'
        ]
    )
    ->timeZoneCode('Europe/Amsterdam')
    ->build();

$usersCompanyLevelApi = $client->getUsersCompanyLevelApi();

try {
    $result = $usersCompanyLevelApi->postCompaniesCompanyIdUsers(
        $companyId,
        $body
    );
    echo 'CreateCompanyUserResponse:';
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
  "id": "S2-5C334C6770",
  "name": {
    "firstName": "John",
    "lastName": "Smith"
  },
  "email": "john.smith@example.com",
  "timeZoneCode": "Europe/Amsterdam",
  "username": "johnsmith",
  "roles": [
    "Merchant standard role",
    "Merchant admin"
  ],
  "active": true,
  "_links": {
    "self": {
      "href": "https://management-test.adyen.com/v1/companies/YOUR_COMPANY_ACCOUNT/users/S2-5C334C6770"
    }
  },
  "associatedMerchantAccounts": [
    "YOUR_MERCHANT_ACCOUNT"
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


# Get-Companies-Company Id-Users-User Id

Returns user details for the `userId` and the `companyId` identified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Users read and write

```php
function getCompaniesCompanyIdUsersUserId(string $companyId, string $userId): CompanyUser
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `userId` | `string` | Template, Required | The unique identifier of the user. |

## Response Type

**200**: OK - the request has succeeded.

[`CompanyUser`](../../doc/models/company-user.md)

## Example Usage

```php
$companyId = 'companyId0';

$userId = 'userId0';

$usersCompanyLevelApi = $client->getUsersCompanyLevelApi();

try {
    $result = $usersCompanyLevelApi->getCompaniesCompanyIdUsersUserId(
        $companyId,
        $userId
    );
    echo 'CompanyUser:';
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


# Patch-Companies-Company Id-Users-User Id

Updates user details for the `userId` and the `companyId` identified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Users read and write

```php
function patchCompaniesCompanyIdUsersUserId(
    string $companyId,
    string $userId,
    ?UpdateCompanyUserRequest $body = null
): CompanyUser
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `userId` | `string` | Template, Required | The unique identifier of the user. |
| `body` | [`?UpdateCompanyUserRequest`](../../doc/models/update-company-user-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CompanyUser`](../../doc/models/company-user.md)

## Example Usage

```php
$companyId = 'companyId0';

$userId = 'userId0';

$usersCompanyLevelApi = $client->getUsersCompanyLevelApi();

try {
    $result = $usersCompanyLevelApi->patchCompaniesCompanyIdUsersUserId(
        $companyId,
        $userId
    );
    echo 'CompanyUser:';
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

