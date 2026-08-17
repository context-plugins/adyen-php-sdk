# Verification

```php
$verificationApi = $client->getVerificationApi();
```

## Class Name

`VerificationApi`

## Methods

* [Post-Check Account Holder](../../doc/controllers/verification.md#post-check-account-holder)
* [Post-Delete Bank Accounts](../../doc/controllers/verification.md#post-delete-bank-accounts)
* [Post-Delete Legal Arrangements](../../doc/controllers/verification.md#post-delete-legal-arrangements)
* [Post-Delete Payout Methods](../../doc/controllers/verification.md#post-delete-payout-methods)
* [Post-Delete Shareholders](../../doc/controllers/verification.md#post-delete-shareholders)
* [Post-Delete Signatories](../../doc/controllers/verification.md#post-delete-signatories)
* [Post-Get Uploaded Documents](../../doc/controllers/verification.md#post-get-uploaded-documents)
* [Post-Upload Document](../../doc/controllers/verification.md#post-upload-document)


# Post-Check Account Holder

Triggers the verification of an account holder even if the checks are not yet required for the volume that they are currently processing.

```php
function postCheckAccountHolder(?PerformVerificationRequest $body = null): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?PerformVerificationRequest`](../../doc/models/perform-verification-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$body = PerformVerificationRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER',
    AccountStateTypeEnum::PROCESSING,
    2
)->build();

$verificationApi = $client->getVerificationApi();

try {
    $result = $verificationApi->postCheckAccountHolder($body);
    echo 'GenericResponse:';
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


# Post-Delete Bank Accounts

Deletes bank accounts associated with an account holder.

```php
function postDeleteBankAccounts(?DeleteBankAccountRequest $body = null): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DeleteBankAccountRequest`](../../doc/models/delete-bank-account-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$body = DeleteBankAccountRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER',
    [
        'eeb6ed22-3bae-483c-83b9-bc2097a75d40'
    ]
)->build();

$verificationApi = $client->getVerificationApi();

try {
    $result = $verificationApi->postDeleteBankAccounts($body);
    echo 'GenericResponse:';
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


# Post-Delete Legal Arrangements

Deletes legal arrangements and/or legal arrangement entities associated with an account holder.

```php
function postDeleteLegalArrangements(?DeleteLegalArrangementRequest $body = null): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DeleteLegalArrangementRequest`](../../doc/models/delete-legal-arrangement-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$body = DeleteLegalArrangementRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER',
    [
        LegalArrangementRequestBuilder::init(
            'cdf92f5a-a114-4ce6-8f19-c3f6ec83141c'
        )->build()
    ]
)->build();

$verificationApi = $client->getVerificationApi();

try {
    $result = $verificationApi->postDeleteLegalArrangements($body);
    echo 'GenericResponse:';
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
  "invalidFields": [],
  "pspReference": "8816080397613514"
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


# Post-Delete Payout Methods

Deletes payout methods associated with an account holder.

```php
function postDeletePayoutMethods(?DeletePayoutMethodRequest $body = null): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DeletePayoutMethodRequest`](../../doc/models/delete-payout-method-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$body = DeletePayoutMethodRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER',
    [
        '34b6ed22-3bae-483c-83b9-bc2097a75d40'
    ]
)->build();

$verificationApi = $client->getVerificationApi();

try {
    $result = $verificationApi->postDeletePayoutMethods($body);
    echo 'GenericResponse:';
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


# Post-Delete Shareholders

Deletes shareholders associated with an account holder.

```php
function postDeleteShareholders(?DeleteShareholderRequest $body = null): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DeleteShareholderRequest`](../../doc/models/delete-shareholder-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$body = DeleteShareholderRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER',
    [
        '9188218c-576e-4cbe-8e86-72722f453920'
    ]
)->build();

$verificationApi = $client->getVerificationApi();

try {
    $result = $verificationApi->postDeleteShareholders($body);
    echo 'GenericResponse:';
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


# Post-Delete Signatories

Deletes signatories associated with an account holder.

```php
function postDeleteSignatories(?DeleteSignatoriesRequest $body = null): GenericResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DeleteSignatoriesRequest`](../../doc/models/delete-signatories-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GenericResponse`](../../doc/models/generic-response.md)

## Example Usage

```php
$verificationApi = $client->getVerificationApi();

try {
    $result = $verificationApi->postDeleteSignatories();
    echo 'GenericResponse:';
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


# Post-Get Uploaded Documents

Returns documents that were previously uploaded for an account holder. Adyen uses the documents during the [verification process](https://docs.adyen.com/classic-platforms/verification-process).

```php
function postGetUploadedDocuments(?GetUploadedDocumentsRequest $body = null): GetUploadedDocumentsResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?GetUploadedDocumentsRequest`](../../doc/models/get-uploaded-documents-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`GetUploadedDocumentsResponse`](../../doc/models/get-uploaded-documents-response.md)

## Example Usage

```php
$body = GetUploadedDocumentsRequestBuilder::init(
    'CODE_OF_ACCOUNT_HOLDER'
)
    ->bankAccountUUID('EXAMPLE_UUID')
    ->build();

$verificationApi = $client->getVerificationApi();

try {
    $result = $verificationApi->postGetUploadedDocuments($body);
    echo 'GetUploadedDocumentsResponse:';
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


# Post-Upload Document

Uploads a document for an account holder. Adyen uses the documents during the [verification process](https://docs.adyen.com/classic-platforms/verification-process).

```php
function postUploadDocument(?UploadDocumentRequest $body = null): UpdateAccountHolderResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?UploadDocumentRequest`](../../doc/models/upload-document-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`UpdateAccountHolderResponse`](../../doc/models/update-account-holder-response.md)

## Example Usage

```php
$body = UploadDocumentRequestBuilder::init(
    'dGVzdCBkb2N1bWVudCBjb250ZW50',
    DocumentDetail1Builder::init(
        DocumentTypeEnum::PASSPORT
    )
        ->accountHolderCode('CODE_OF_ACCOUNT_HOLDER')
        ->description('test passport description')
        ->filename('passport.png')
        ->build()
)->build();

$verificationApi = $client->getVerificationApi();

try {
    $result = $verificationApi->postUploadDocument($body);
    echo 'UpdateAccountHolderResponse:';
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

