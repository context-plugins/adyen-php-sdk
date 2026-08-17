# Directdebitmandates

```php
$directdebitmandatesApi = $client->getDirectdebitmandatesApi();
```

## Class Name

`DirectdebitmandatesApi`

## Methods

* [Get-Mandates](../../doc/controllers/directdebitmandates.md#get-mandates)
* [Get-Mandates-Mandate Id](../../doc/controllers/directdebitmandates.md#get-mandates-mandate-id)
* [Patch-Mandates-Mandate Id](../../doc/controllers/directdebitmandates.md#patch-mandates-mandate-id)
* [Post-Mandates-Mandate Id-Cancel](../../doc/controllers/directdebitmandates.md#post-mandates-mandate-id-cancel)


# Get-Mandates

Returns a list of all [direct debit mandates](https://docs.adyen.com/business-accounts/accept-direct-debits-uk) created for a business account.

:information_source: **Note** This endpoint does not require authentication.

```php
function getMandates(
    ?string $balanceAccountId = null,
    ?string $paymentInstrumentId = null,
    ?string $cursor = null
): ListMandatesResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balanceAccountId` | `?string` | Query, Optional | The unique identifier of the balance account linked to the payment instrument. |
| `paymentInstrumentId` | `?string` | Query, Optional | The unique identifier of the payment instrument linked to the mandate. |
| `cursor` | `?string` | Query, Optional | The pagination cursor returned in a previous GET `/mandates` request. |

## Response Type

**200**: OK - The request has succeeded

[`ListMandatesResponse`](../../doc/models/list-mandates-response.md)

## Example Usage

```php
$directDebitMandatesApi = $client->getDirectDebitMandatesApi();

try {
    $result = $directDebitMandatesApi->getMandates();
    echo 'ListMandatesResponse:';
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
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Mandates-Mandate Id

Returns the details of the specified [direct debit mandate](https://docs.adyen.com/business-accounts/accept-direct-debits-uk).

:information_source: **Note** This endpoint does not require authentication.

```php
function getMandatesMandateId(string $mandateId): Mandate1
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandateId` | `string` | Template, Required | The unique identifier of the mandate. |

## Response Type

**200**: OK - The request has succeeded

[`Mandate1`](../../doc/models/mandate-1.md)

## Example Usage

```php
$mandateId = 'mandateId8';

$directDebitMandatesApi = $client->getDirectDebitMandatesApi();

try {
    $result = $directDebitMandatesApi->getMandatesMandateId($mandateId);
    echo 'Mandate1:';
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
| 404 | The mandate was not found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Patch-Mandates-Mandate Id

Amend the specified [direct debit mandate](https://docs.adyen.com/business-accounts/accept-direct-debits-uk).

:information_source: **Note** This endpoint does not require authentication.

```php
function patchMandatesMandateId(string $mandateId, MandateUpdate $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandateId` | `string` | Template, Required | The unique identifier of the mandate. |
| `body` | [`MandateUpdate`](../../doc/models/mandate-update.md) | Body, Required | - |

## Response Type

**202**: Accepted - The request has been accepted

`void`

## Example Usage

```php
$mandateId = 'mandateId8';

$body = MandateUpdateBuilder::init()->build();

$directDebitMandatesApi = $client->getDirectDebitMandatesApi();

try {
    $directDebitMandatesApi->patchMandatesMandateId(
        $mandateId,
        $body
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
| 404 | The mandate was not found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Mandates-Mandate Id-Cancel

Cancel a specified [direct debit mandate](https://docs.adyen.com/business-accounts/accept-direct-debits-uk).

:information_source: **Note** This endpoint does not require authentication.

```php
function postMandatesMandateIdCancel(string $mandateId): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mandateId` | `string` | Template, Required | The unique identifier of the mandate. |

## Response Type

**202**: Accepted - The request has been accepted

`void`

## Example Usage

```php
$mandateId = 'mandateId8';

$directDebitMandatesApi = $client->getDirectDebitMandatesApi();

try {
    $directDebitMandatesApi->postMandatesMandateIdCancel($mandateId);
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
| 404 | The mandate was not found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

