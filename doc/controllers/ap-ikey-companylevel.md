# AP Ikey-Companylevel

```php
$aPIkeyCompanylevelApi = $client->getAPIkeyCompanylevelApi();
```

## Class Name

`APIkeyCompanylevelApi`


# Post-Companies-Company Id-Api Credentials-Api Credential Id-Generate Api Key

Returns a new API key for the API credential. You can use the new API key a few minutes after generating it. The old API key stops working 24 hours after generating a new one.

To make this request, your API credential must have the following [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—API credentials read and write

```php
function postCompaniesCompanyIdApiCredentialsApiCredentialIdGenerateApiKey(
    string $companyId,
    string $apiCredentialId
): GenerateApiKeyResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `apiCredentialId` | `string` | Template, Required | Unique identifier of the API credential. |

## Response Type

**200**: OK - the request has succeeded.

[`GenerateApiKeyResponse`](../../doc/models/generate-api-key-response.md)

## Example Usage

```php
$companyId = 'companyId0';

$apiCredentialId = 'apiCredentialId8';

$aPIKeyCompanyLevelApi = $client->getAPIKeyCompanyLevelApi();

try {
    $result = $aPIKeyCompanyLevelApi->postCompaniesCompanyIdApiCredentialsApiCredentialIdGenerateApiKey(
        $companyId,
        $apiCredentialId
    );
    echo 'GenerateApiKeyResponse:';
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

