# Grantoffers

```php
$grantoffersApi = $client->getGrantoffersApi();
```

## Class Name

`GrantoffersApi`

## Methods

* [Get-Grant Offers](../../doc/controllers/grantoffers.md#get-grant-offers)
* [Get-Grant Offers-Grant Offer Id](../../doc/controllers/grantoffers.md#get-grant-offers-grant-offer-id)
* [Get-Grant Offers 1](../../doc/controllers/grantoffers.md#get-grant-offers-1)
* [Get-Grant Offers-Id](../../doc/controllers/grantoffers.md#get-grant-offers-id)


# Get-Grant Offers

**This endpoint is deprecated.**

Returns a list of all [grant offers](https://docs.adyen.com/platforms/capital#grant-offers) available for `accountHolderId` specified as a query parameter.

```php
function getGrantOffers(string $accountHolderId): GrantOffers
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accountHolderId` | `string` | Query, Required | The unique identifier of the grant account. |

## Response Type

**200**: OK - the request has succeeded.

[`GrantOffers`](../../doc/models/grant-offers.md)

## Example Usage

```php
$accountHolderId = 'accountHolderId8';

$grantOffersApi = $client->getGrantOffersApi();

try {
    $result = $grantOffersApi->getGrantOffers($accountHolderId);
    echo 'GrantOffers:';
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


# Get-Grant Offers-Grant Offer Id

**This endpoint is deprecated.**

Returns the details of a single grant offer.

```php
function getGrantOffersGrantOfferId(string $grantOfferId): GrantOffer
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `grantOfferId` | `string` | Template, Required | The unique identifier of the grant offer. |

## Response Type

**200**: OK - the request has succeeded.

[`GrantOffer`](../../doc/models/grant-offer.md)

## Example Usage

```php
$grantOfferId = 'grantOfferId6';

$grantOffersApi = $client->getGrantOffersApi();

try {
    $result = $grantOffersApi->getGrantOffersGrantOfferId($grantOfferId);
    echo 'GrantOffer:';
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


# Get-Grant Offers 1

Returns a list of all [static offers](https://docs.adyen.com/capital/get-grant-offers/static-offers) available for `accountHolderId` specified as a query parameter. This also includes static offers created for financing amounts that the user selected from [dynamic offers](https://docs.adyen.com/capital/get-grant-offers/dynamic-offers/).

:information_source: **Note** This endpoint does not require authentication.

```php
function getGrantOffers1(string $accountHolderId): GrantOffers
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accountHolderId` | `string` | Query, Required | The unique identifier of the account holder for which you want to get the available static offers.<br><br>**Constraints**: *Minimum Length*: `1` |

## Response Type

**200**: OK - The request has succeeded.

[`GrantOffers`](../../doc/models/grant-offers.md)

## Example Usage

```php
$accountHolderId = 'accountHolderId8';

$grantOffersApi = $client->getGrantOffersApi();

try {
    $result = $grantOffersApi->getGrantOffers1($accountHolderId);
    echo 'GrantOffers:';
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


# Get-Grant Offers-Id

Returns the details of the specified static offer.

:information_source: **Note** This endpoint does not require authentication.

```php
function getGrantOffersId(string $id): GrantOffer1
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the static offer. |

## Response Type

**200**: OK - The request has succeeded.

[`GrantOffer1`](../../doc/models/grant-offer-1.md)

## Example Usage

```php
$id = 'id0';

$grantOffersApi = $client->getGrantOffersApi();

try {
    $result = $grantOffersApi->getGrantOffersId($id);
    echo 'GrantOffer1:';
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

