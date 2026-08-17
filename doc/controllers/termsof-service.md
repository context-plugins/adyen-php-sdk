# Termsof Service

```php
$termsofServiceApi = $client->getTermsofServiceApi();
```

## Class Name

`TermsofServiceApi`

## Methods

* [Get-Legal Entities-Id-Accepted Terms of Service Document-Termsofserviceacceptancereference](../../doc/controllers/termsof-service.md#get-legal-entities-id-accepted-terms-of-service-document-termsofserviceacceptancereference)
* [Post-Legal Entities-Id-Terms of Service](../../doc/controllers/termsof-service.md#post-legal-entities-id-terms-of-service)
* [Patch-Legal Entities-Id-Terms of Service-Termsofservicedocumentid](../../doc/controllers/termsof-service.md#patch-legal-entities-id-terms-of-service-termsofservicedocumentid)
* [Get-Legal Entities-Id-Terms of Service Acceptance Infos](../../doc/controllers/termsof-service.md#get-legal-entities-id-terms-of-service-acceptance-infos)
* [Get-Legal Entities-Id-Terms of Service Status](../../doc/controllers/termsof-service.md#get-legal-entities-id-terms-of-service-status)


# Get-Legal Entities-Id-Accepted Terms of Service Document-Termsofserviceacceptancereference

Returns the accepted Terms of Service document for a legal entity.

Requests to this endpoint are subject to rate limits:

- Live environments: 700 requests per 5 seconds.

- Test environments: 200 requests per 5 seconds.

- Failed requests are subject to a limit of 5 failures per 10 seconds.

```php
function getLegalEntitiesIdAcceptedTermsOfServiceDocumentTermsofserviceacceptancereference(
    string $id,
    string $termsofserviceacceptancereference,
    ?string $termsOfServiceDocumentFormat = null
): GetAcceptedTermsOfServiceDocumentResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the legal entity. For sole proprietorship, this is the individual legal entity ID of the owner. For organizations, this is the ID of the organization. |
| `termsofserviceacceptancereference` | `string` | Template, Required | An Adyen-generated reference for the accepted Terms of Service. |
| `termsOfServiceDocumentFormat` | `?string` | Query, Optional | The format of the Terms of Service document. Possible values: **JSON**, **PDF**, or **TXT** |

## Response Type

**200**: OK - the request has succeeded.

[`GetAcceptedTermsOfServiceDocumentResponse`](../../doc/models/get-accepted-terms-of-service-document-response.md)

## Example Usage

```php
$id = 'id0';

$termsofserviceacceptancereference = 'termsofserviceacceptancereference8';

$termsOfServiceApi = $client->getTermsOfServiceApi();

try {
    $result = $termsOfServiceApi->getLegalEntitiesIdAcceptedTermsOfServiceDocumentTermsofserviceacceptancereference(
        $id,
        $termsofserviceacceptancereference
    );
    echo 'GetAcceptedTermsOfServiceDocumentResponse:';
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


# Post-Legal Entities-Id-Terms of Service

Returns the Terms of Service document for a legal entity.

Requests to this endpoint are subject to rate limits:

- Live environments: 700 requests per 5 seconds.

- Test environments: 200 requests per 5 seconds.

- Failed requests are subject to a limit of 5 failures per 10 seconds.

```php
function postLegalEntitiesIdTermsOfService(
    string $id,
    ?GetTermsOfServiceDocumentRequest $body = null
): GetTermsOfServiceDocumentResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the legal entity. For sole proprietorships, this is the individual legal entity ID of the owner. For organizations, this is the ID of the organization. |
| `body` | [`?GetTermsOfServiceDocumentRequest`](../../doc/models/get-terms-of-service-document-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetTermsOfServiceDocumentResponse`](../../doc/models/get-terms-of-service-document-response.md)

## Example Usage

```php
$id = 'id0';

$body = GetTermsOfServiceDocumentRequestBuilder::init(
    'en',
    Type64Enum::ADYENISSUING
)->build();

$termsOfServiceApi = $client->getTermsOfServiceApi();

try {
    $result = $termsOfServiceApi->postLegalEntitiesIdTermsOfService(
        $id,
        $body
    );
    echo 'GetTermsOfServiceDocumentResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "LE00000000000000000000001",
  "type": "adyenIssuing",
  "language": "en",
  "document": "JVBERi0xLjQKJcOkw7zDtsOfCjIgMCBv+f/ub0j6JPRX+E3EmC==",
  "termsOfServiceDocumentId": "abc123",
  "termsOfServiceDocumentFormat": "JSON"
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


# Patch-Legal Entities-Id-Terms of Service-Termsofservicedocumentid

Accepts Terms of Service.

Requests to this endpoint are subject to rate limits:

- Live environments: 700 requests per 5 seconds.

- Test environments: 200 requests per 5 seconds.

- Failed requests are subject to a limit of 5 failures per 10 seconds.

```php
function patchLegalEntitiesIdTermsOfServiceTermsofservicedocumentid(
    string $id,
    string $termsofservicedocumentid,
    ?AcceptTermsOfServiceRequest $body = null
): AcceptTermsOfServiceResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the legal entity.<br><br>For sole proprietorships, this is the individual legal entity ID of the owner.<br><br>For organizations, this is the ID of the organization.<br><br>For legal representatives of individuals, this is the ID of the individual. |
| `termsofservicedocumentid` | `string` | Template, Required | The unique identifier of the Terms of Service document. |
| `body` | [`?AcceptTermsOfServiceRequest`](../../doc/models/accept-terms-of-service-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`AcceptTermsOfServiceResponse`](../../doc/models/accept-terms-of-service-response.md)

## Example Usage

```php
$id = 'id0';

$termsofservicedocumentid = 'termsofservicedocumentid2';

$body = AcceptTermsOfServiceRequestBuilder::init(
    'LE00000000000000000000002'
)->build();

$termsOfServiceApi = $client->getTermsOfServiceApi();

try {
    $result = $termsOfServiceApi->patchLegalEntitiesIdTermsOfServiceTermsofservicedocumentid(
        $id,
        $termsofservicedocumentid,
        $body
    );
    echo 'AcceptTermsOfServiceResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "acceptedBy": "LE00000000000000000000002",
  "id": "TOSA000AB00000000B2AAAB2BA0AA0",
  "language": "en",
  "termsOfServiceDocumentId": "abc123",
  "type": "adyenIssuing"
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


# Get-Legal Entities-Id-Terms of Service Acceptance Infos

Returns Terms of Service information for a legal entity.

Requests to this endpoint are subject to rate limits:

- Live environments: 700 requests per 5 seconds.

- Test environments: 200 requests per 5 seconds.

- Failed requests are subject to a limit of 5 failures per 10 seconds.

```php
function getLegalEntitiesIdTermsOfServiceAcceptanceInfos(string $id): GetTermsOfServiceAcceptanceInfosResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the legal entity. For sole proprietorships, this is the individual legal entity ID of the owner. For organizations, this is the ID of the organization. |

## Response Type

**200**: OK - the request has succeeded.

[`GetTermsOfServiceAcceptanceInfosResponse`](../../doc/models/get-terms-of-service-acceptance-infos-response.md)

## Example Usage

```php
$id = 'id0';

$termsOfServiceApi = $client->getTermsOfServiceApi();

try {
    $result = $termsOfServiceApi->getLegalEntitiesIdTermsOfServiceAcceptanceInfos($id);
    echo 'GetTermsOfServiceAcceptanceInfosResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "data": [
    {
      "acceptedBy": "LE00000000000000000000002",
      "acceptedFor": "LE00000000000000000000001",
      "createdAt": "2022-12-05T13:36:58.212253Z",
      "id": "TOSA000AB00000000B2AAAB2BA0AA0",
      "type": "adyenIssuing"
    }
  ]
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


# Get-Legal Entities-Id-Terms of Service Status

Returns the required types of Terms of Service that need to be accepted by a legal entity.

Requests to this endpoint are subject to rate limits:

- Live environments: 700 requests per 5 seconds.

- Test environments: 200 requests per 5 seconds.

- Failed requests are subject to a limit of 5 failures per 10 seconds.

```php
function getLegalEntitiesIdTermsOfServiceStatus(string $id): CalculateTermsOfServiceStatusResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the legal entity. For sole proprietorships, this is the individual legal entity ID of the owner. For organizations, this is the ID of the organization. |

## Response Type

**200**: OK - the request has succeeded.

[`CalculateTermsOfServiceStatusResponse`](../../doc/models/calculate-terms-of-service-status-response.md)

## Example Usage

```php
$id = 'id0';

$termsOfServiceApi = $client->getTermsOfServiceApi();

try {
    $result = $termsOfServiceApi->getLegalEntitiesIdTermsOfServiceStatus($id);
    echo 'CalculateTermsOfServiceStatusResponse:';
    var_dump($result);
} catch (ServiceErrorError1Exception $exp) {
    echo 'Caught ServiceErrorError1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "termsOfServiceTypes": [
    "adyenIssuing"
  ]
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

