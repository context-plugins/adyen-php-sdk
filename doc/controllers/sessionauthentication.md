# Sessionauthentication

```php
$sessionauthenticationApi = $client->getSessionauthenticationApi();
```

## Class Name

`SessionauthenticationApi`

## Methods

* [Post-Sessions](../../doc/controllers/sessionauthentication.md#post-sessions)
* [Post-Auth-Certificate](../../doc/controllers/sessionauthentication.md#post-auth-certificate)


# Post-Sessions

Creates a session token that is required to integrate [components](https://docs.adyen.com/platforms/components-overview).

The response contains encrypted session data. The front end then uses the session data to make the required server-side calls for the component.

To create a token, you must meet specific requirements. These requirements vary depending on the type of component. For more information, see the documentation for [Onboarding](https://docs.adyen.com/platforms/onboard-users/components) and [Platform Experience](https://docs.adyen.com/platforms/build-user-dashboards) components.

:information_source: **Note** This endpoint does not require authentication.

```php
function postSessions(AuthenticationSessionRequest $body): AuthenticationSessionResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AuthenticationSessionRequest`](../../doc/models/authentication-session-request.md) | Body, Required | - |

## Response Type

**200**: Successful operation

[`AuthenticationSessionResponse`](../../doc/models/authentication-session-response.md)

## Example Usage

```php
$body = AuthenticationSessionRequestBuilder::init(
    'https://www.your-website.com',
    Policy2Builder::init()
        ->resources(
            [
                LegalEntityResourceBuilder::init(
                    'LE00000000000000000000001'
                )
                    ->type('legalEntity')
                    ->build()
            ]
        )
        ->roles(
            [
                'createTransferInstrumentComponent',
                'manageTransferInstrumentComponent'
            ]
        )
        ->build(),
    ProductType2Enum::ONBOARDING
)->build();

$sessionAuthenticationApi = $client->getSessionAuthenticationApi();

try {
    $result = $sessionAuthenticationApi->postSessions($body);
    echo 'AuthenticationSessionResponse:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "11a1e60a-18b0-4dda-9258-e0ae29e1e2a3",
  "token": "eyJraWQiOiJwbGF0Zm9ybWNvbGRlciI..."
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Auth-Certificate

Establishes a secure communication session between the Mobile SDK and the Adyen payments platform, through mutual authentication. The request sends a setup token that identifies the SDK and the device. The response returns a session token that the SDK can use to authenticate responses received from the Adyen payments platform.

:information_source: **Note** This endpoint does not require authentication.

```php
function postAuthCertificate(
    ?string $xAPIKey = null,
    ?CertificateLoadingRequest $body = null
): CertificateLoadingResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xAPIKey` | `?string` | Header, Optional | The API key to authenticate API requests. |
| `body` | [`?CertificateLoadingRequest`](../../doc/models/certificate-loading-request.md) | Body, Optional | - |

## Response Type

**201**: OK - the request has succeeded.

[`CertificateLoadingResponse`](../../doc/models/certificate-loading-response.md)

## Example Usage

```php
$body = CertificateLoadingRequestBuilder::init(
    'YOUR_MERCHANT_ACCOUNT',
    'SETUP_TOKEN'
)
    ->store('YOUR_STORE_REFERENCE')
    ->build();

$sessionAuthenticationApi = $client->getSessionAuthenticationApi();

try {
    $result = $sessionAuthenticationApi->postAuthCertificate(
        null,
        $body
    );
    echo 'CertificateLoadingResponse:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "id": "APP_SESSION_ID",
  "installationId": "INSTALLATION_ID",
  "merchantAccount": "YOUR_MERCHANT_ACCOUNT",
  "store": "YOUR_STORE_REFERENCE",
  "sdkData": "SDK_DATA_BLOB"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request - validation failed. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable entity - session request could not be processed. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal server error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

