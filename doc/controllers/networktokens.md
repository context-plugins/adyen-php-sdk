# Networktokens

```php
$networktokensApi = $client->getNetworktokensApi();
```

## Class Name

`NetworktokensApi`

## Methods

* [Get-Network Tokens-Network Token Id](../../doc/controllers/networktokens.md#get-network-tokens-network-token-id)
* [Patch-Network Tokens-Network Token Id](../../doc/controllers/networktokens.md#patch-network-tokens-network-token-id)


# Get-Network Tokens-Network Token Id

Returns the details of a network token.

```php
function getNetworkTokensNetworkTokenId(string $networkTokenId): GetNetworkTokenResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `networkTokenId` | `string` | Template, Required | The unique identifier of the network token. |

## Response Type

**200**: OK - the request has succeeded.

[`GetNetworkTokenResponse`](../../doc/models/get-network-token-response.md)

## Example Usage

```php
$networkTokenId = 'networkTokenId4';

$networkTokensApi = $client->getNetworkTokensApi();

try {
    $result = $networkTokensApi->getNetworkTokensNetworkTokenId($networkTokenId);
    echo 'GetNetworkTokenResponse:';
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
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |


# Patch-Network Tokens-Network Token Id

Updates the status of the network token.

```php
function patchNetworkTokensNetworkTokenId(string $networkTokenId, ?UpdateNetworkTokenRequest $body = null): void
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `networkTokenId` | `string` | Template, Required | The unique identifier of the network token. |
| `body` | [`?UpdateNetworkTokenRequest`](../../doc/models/update-network-token-request.md) | Body, Optional | - |

## Response Type

**202**: No Content - look at the actual response code for the status of the request.

`void`

## Example Usage

```php
$networkTokenId = 'networkTokenId4';

$networkTokensApi = $client->getNetworkTokensApi();

try {
    $networkTokensApi->patchNetworkTokensNetworkTokenId($networkTokenId);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |

