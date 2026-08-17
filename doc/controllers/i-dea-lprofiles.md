# I DEA Lprofiles

```php
$iDEALprofilesApi = $client->getIDEALprofilesApi();
```

## Class Name

`IDEALprofilesApi`

## Methods

* [Post-Ideal-Profile-Auth-Link](../../doc/controllers/i-dea-lprofiles.md#post-ideal-profile-auth-link)
* [Post-Ideal-Profile-Authenticate](../../doc/controllers/i-dea-lprofiles.md#post-ideal-profile-authenticate)
* [Post-Ideal-Profile-Register](../../doc/controllers/i-dea-lprofiles.md#post-ideal-profile-register)


# Post-Ideal-Profile-Auth-Link

Manage an already registered iDEAL profile. Generates a redirection URL to manage the iDEAL profile linked to the account holder from the request.

:information_source: **Note** This endpoint does not require authentication.

```php
function postIdealProfileAuthLink(IdealAuthLinkRequest $body): IdealAuthLinkResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`IdealAuthLinkRequest`](../../doc/models/ideal-auth-link-request.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`IdealAuthLinkResponse`](../../doc/models/ideal-auth-link-response.md)

## Example Usage

```php
$body = IdealAuthLinkRequestBuilder::init(
    'AH00000000000000000000000'
)->build();

$iDEALProfilesApi = $client->getIDEALProfilesApi();

try {
    $result = $iDEALProfilesApi->postIdealProfileAuthLink($body);
    echo 'IdealAuthLinkResponse:';
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
  "redirectUrl": {
    "href": "https://ideal.auth/someUrl"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request is malformed or is not the expected format. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Service Error - An unrecoverable error occurred while trying to perform the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Ideal-Profile-Authenticate

Generates an redirection URL to finish the authentication flow when requested by iDEAL. Before calling this endpoint, make sure that your user has completed multi-factor authentication.

:information_source: **Note** This endpoint does not require authentication.

```php
function postIdealProfileAuthenticate(IdealAuthenticateRequest $body): IdealAuthenticateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`IdealAuthenticateRequest`](../../doc/models/ideal-authenticate-request.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`IdealAuthenticateResponse`](../../doc/models/ideal-authenticate-response.md)

## Example Usage

```php
$body = IdealAuthenticateRequestBuilder::init(
    'AH00000000000000000000000',
    'https://ideal.auth/somePayload'
)->build();

$iDEALProfilesApi = $client->getIDEALProfilesApi();

try {
    $result = $iDEALProfilesApi->postIdealProfileAuthenticate($body);
    echo 'IdealAuthenticateResponse:';
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
  "redirectUrl": {
    "href": "https://ideal.auth/someUrl"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request is malformed or is not the expected format. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Service Error - An unrecoverable error occurred while trying to perform the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Ideal-Profile-Register

Register a new iDEAL profile. The profile is linked to the account holder and payment instruments included in the request. The user must be redirected to the URL in the response to finish their IDEAL profile registration.

:information_source: **Note** This endpoint does not require authentication.

```php
function postIdealProfileRegister(ProfileRegistrationRequest $body): ProfileRegistrationResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ProfileRegistrationRequest`](../../doc/models/profile-registration-request.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`ProfileRegistrationResponse`](../../doc/models/profile-registration-response.md)

## Example Usage

```php
$body = ProfileRegistrationRequestBuilder::init(
    'AH00000000000000000000000',
    [
        'PI00000000000000000000000',
        'PI11111111111111111111111'
    ]
)->build();

$iDEALProfilesApi = $client->getIDEALProfilesApi();

try {
    $result = $iDEALProfilesApi->postIdealProfileRegister($body);
    echo 'ProfileRegistrationResponse:';
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
  "redirectUrl": {
    "href": "https://ideal.auth/someUrl"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request is malformed or is not the expected format. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Service Error - An unrecoverable error occurred while trying to perform the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

