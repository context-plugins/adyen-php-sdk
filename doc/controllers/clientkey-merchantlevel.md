# Clientkey-Merchantlevel

```php
$clientkeyMerchantlevelApi = $client->getClientkeyMerchantlevelApi();
```

## Class Name

`ClientkeyMerchantlevelApi`


# Post-Merchants-Merchant Id-Api Credentials-Api Credential Id-Generate Client Key

Returns a new [client key](https://docs.adyen.com/development-resources/client-side-authentication#how-it-works) for the API credential identified in the path. You can use the new client key a few minutes after generating it. The old client key stops working 24 hours after generating a new one.

To make this request, your API credential must have the following [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—API credentials read and write

```php
function postMerchantsMerchantIdApiCredentialsApiCredentialIdGenerateClientKey(
    string $merchantId,
    string $apiCredentialId
): GenerateClientKeyResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `apiCredentialId` | `string` | Template, Required | Unique identifier of the API credential. |

## Response Type

**200**: OK - the request has succeeded.

[`GenerateClientKeyResponse`](../../doc/models/generate-client-key-response.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$apiCredentialId = 'apiCredentialId8';

$clientKeyMerchantLevelApi = $client->getClientKeyMerchantLevelApi();

try {
    $result = $clientKeyMerchantLevelApi->postMerchantsMerchantIdApiCredentialsApiCredentialIdGenerateClientKey(
        $merchantId,
        $apiCredentialId
    );
    echo 'GenerateClientKeyResponse:';
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

