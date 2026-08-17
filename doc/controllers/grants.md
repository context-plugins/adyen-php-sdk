# Grants

```php
$grantsApi = $client->getGrantsApi();
```

## Class Name

`GrantsApi`

## Methods

* [Get-Grants](../../doc/controllers/grants.md#get-grants)
* [Post-Grants](../../doc/controllers/grants.md#post-grants)
* [Get-Grants-Grant Id](../../doc/controllers/grants.md#get-grants-grant-id)
* [Get-Grants-Grant Id-Disbursements](../../doc/controllers/grants.md#get-grants-grant-id-disbursements)
* [Get-Grants-Grant Id-Disbursements-Disbursement Id](../../doc/controllers/grants.md#get-grants-grant-id-disbursements-disbursement-id)
* [Patch-Grants-Grant Id-Disbursements-Disbursement Id](../../doc/controllers/grants.md#patch-grants-grant-id-disbursements-disbursement-id)


# Get-Grants

Returns a list of all the grants of a specific account holder.

:information_source: **Note** This endpoint does not require authentication.

```php
function getGrants(string $counterpartyAccountHolderId): Grants
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `counterpartyAccountHolderId` | `string` | Query, Required | The unique identifier of the account holder that received the grants. |

## Response Type

**200**: OK - The request has succeeded.

[`Grants`](../../doc/models/grants.md)

## Example Usage

```php
$counterpartyAccountHolderId = 'counterpartyAccountHolderId8';

$grantsApi = $client->getGrantsApi();

try {
    $result = $grantsApi->getGrants($counterpartyAccountHolderId);
    echo 'Grants:';
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


# Post-Grants

Make a request for a grant on behalf of an account holder.

:information_source: **Note** This endpoint does not require authentication.

```php
function postGrants(?CapitalGrantInfo $body = null): Grant
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CapitalGrantInfo`](../../doc/models/capital-grant-info.md) | Body, Optional | - |

## Response Type

**200**: OK - The request has succeeded.

[`Grant`](../../doc/models/grant.md)

## Example Usage

```php
$grantsApi = $client->getGrantsApi();

try {
    $result = $grantsApi->postGrants();
    echo 'Grant:';
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
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Grants-Grant Id

Returns the details of the specified grant.

:information_source: **Note** This endpoint does not require authentication.

```php
function getGrantsGrantId(string $grantId): Grant
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `grantId` | `string` | Template, Required | The unique identifier of the grant reference. |

## Response Type

**200**: OK - The request has succeeded.

[`Grant`](../../doc/models/grant.md)

## Example Usage

```php
$grantId = 'grantId8';

$grantsApi = $client->getGrantsApi();

try {
    $result = $grantsApi->getGrantsGrantId($grantId);
    echo 'Grant:';
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


# Get-Grants-Grant Id-Disbursements

Returns the disbursements of a specified grant.

:information_source: **Note** This endpoint does not require authentication.

```php
function getGrantsGrantIdDisbursements(string $grantId): Disbursements
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `grantId` | `string` | Template, Required | The unique identifier of the grant reference. |

## Response Type

**200**: OK - The request has succeeded.

[`Disbursements`](../../doc/models/disbursements.md)

## Example Usage

```php
$grantId = 'grantId8';

$grantsApi = $client->getGrantsApi();

try {
    $result = $grantsApi->getGrantsGrantIdDisbursements($grantId);
    echo 'Disbursements:';
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


# Get-Grants-Grant Id-Disbursements-Disbursement Id

Returns the details of a disbursement specified in the path.

:information_source: **Note** This endpoint does not require authentication.

```php
function getGrantsGrantIdDisbursementsDisbursementId(string $grantId, string $disbursementId): Disbursement
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `grantId` | `string` | Template, Required | The unique identifier of the grant reference. |
| `disbursementId` | `string` | Template, Required | The unique identifier of the disbursement. |

## Response Type

**200**: OK - The request has succeeded.

[`Disbursement`](../../doc/models/disbursement.md)

## Example Usage

```php
$grantId = 'grantId8';

$disbursementId = 'disbursementId8';

$grantsApi = $client->getGrantsApi();

try {
    $result = $grantsApi->getGrantsGrantIdDisbursementsDisbursementId(
        $grantId,
        $disbursementId
    );
    echo 'Disbursement:';
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


# Patch-Grants-Grant Id-Disbursements-Disbursement Id

Update the percentage of your user's net income that is deducted for repaying the grant.

:information_source: **Note** This endpoint does not require authentication.

```php
function patchGrantsGrantIdDisbursementsDisbursementId(
    string $grantId,
    string $disbursementId,
    DisbursementInfoUpdate $body
): Disbursement
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `grantId` | `string` | Template, Required | The unique identifier of the grant reference.<br><br>**Constraints**: *Minimum Length*: `1` |
| `disbursementId` | `string` | Template, Required | The unique identifier of the disbursement.<br><br>**Constraints**: *Minimum Length*: `1` |
| `body` | [`DisbursementInfoUpdate`](../../doc/models/disbursement-info-update.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`Disbursement`](../../doc/models/disbursement.md)

## Example Usage

```php
$grantId = 'grantId8';

$disbursementId = 'disbursementId8';

$body = DisbursementInfoUpdateBuilder::init()->build();

$grantsApi = $client->getGrantsApi();

try {
    $result = $grantsApi->patchGrantsGrantIdDisbursementsDisbursementId(
        $grantId,
        $disbursementId,
        $body
    );
    echo 'Disbursement:';
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

