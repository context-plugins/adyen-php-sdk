# Manage SC Adevices

```php
$manageSCAdevicesApi = $client->getManageSCAdevicesApi();
```

## Class Name

`ManageSCAdevicesApi`

## Methods

* [Get-Registered Devices](../../doc/controllers/manage-sc-adevices.md#get-registered-devices)
* [Post-Registered Devices](../../doc/controllers/manage-sc-adevices.md#post-registered-devices)
* [Post-Registered Devices-Device Id-Associations](../../doc/controllers/manage-sc-adevices.md#post-registered-devices-device-id-associations)
* [Patch-Registered Devices-Device Id-Associations](../../doc/controllers/manage-sc-adevices.md#patch-registered-devices-device-id-associations)
* [Delete-Registered Devices-Id](../../doc/controllers/manage-sc-adevices.md#delete-registered-devices-id)
* [Patch-Registered Devices-Id](../../doc/controllers/manage-sc-adevices.md#patch-registered-devices-id)


# Get-Registered Devices

Get a paginated list of the SCA devices you have currently registered for a specific payment instrument.

```php
function getRegisteredDevices(
    string $paymentInstrumentId,
    ?int $pageNumber = null,
    ?int $pageSize = null
): SearchRegisteredDevicesResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Query, Required | The unique identifier of a payment instrument. It limits the returned list to SCA devices associated to this payment instrument. |
| `pageNumber` | `?int` | Query, Optional | The index of the page to retrieve. The index of the first page is 0 (zero).<br><br>Default: 0. |
| `pageSize` | `?int` | Query, Optional | The number of items to have on a page.<br><br>Default: 20. Maximum: 100. |

## Response Type

**200**: OK - the request has succeeded.

[`SearchRegisteredDevicesResponse`](../../doc/models/search-registered-devices-response.md)

## Example Usage

```php
$paymentInstrumentId = 'paymentInstrumentId2';

$manageSCADevicesApi = $client->getManageSCADevicesApi();

try {
    $result = $manageSCADevicesApi->getRegisteredDevices($paymentInstrumentId);
    echo 'SearchRegisteredDevicesResponse:';
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


# Post-Registered Devices

Initiates the registration of a user's device for Strong Customer Authentication (SCA). You can register SCA devices for [business accounts](https://docs.adyen.com/platforms/business-accounts/sca/register-devices) or [Adyen-issued cards](https://docs.adyen.com/issuing/3d-secure/oob-auth-sdk/register-devices).

For a successful request, the device must be eligible for SCA.

```php
function postRegisteredDevices(?RegisterSCARequest $body = null): RegisterSCAResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?RegisterSCARequest`](../../doc/models/register-sca-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`RegisterSCAResponse`](../../doc/models/register-sca-response.md)

## Example Usage

```php
$manageSCADevicesApi = $client->getManageSCADevicesApi();

try {
    $result = $manageSCADevicesApi->postRegisteredDevices();
    echo 'RegisterSCAResponse:';
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


# Post-Registered Devices-Device Id-Associations

Initiates an association between a user's registered SCA device and an Adyen resource. For example, you can associate an SCA device with additional [business accounts](https://docs.adyen.com/platforms/business-accounts/sca/register-devices) or [Adyen-issued cards](https://docs.adyen.com/issuing/3d-secure/oob-auth-sdk/register-devices).

```php
function postRegisteredDevicesDeviceIdAssociations(
    string $deviceId,
    ?AssociationInitiateRequest $body = null
): AssociationInitiateResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `string` | Template, Required | The unique identifier of the SCA device that you are associating with a resource. |
| `body` | [`?AssociationInitiateRequest`](../../doc/models/association-initiate-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`AssociationInitiateResponse`](../../doc/models/association-initiate-response.md)

## Example Usage

```php
$deviceId = 'deviceId0';

$body = AssociationInitiateRequestBuilder::init(
    [
        'ids7',
        'ids8',
        'ids9'
    ]
)->build();

$manageSCADevicesApi = $client->getManageSCADevicesApi();

try {
    $result = $manageSCADevicesApi->postRegisteredDevicesDeviceIdAssociations(
        $deviceId,
        $body
    );
    echo 'AssociationInitiateResponse:';
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


# Patch-Registered Devices-Device Id-Associations

Completes an association between a user's registered SCA device and an Adyen resource. For example, you can associate an SCA device with additional [business accounts](https://docs.adyen.com/platforms/business-accounts/sca/register-devices) or [Adyen-issued cards](https://docs.adyen.com/issuing/3d-secure/oob-auth-sdk/register-devices).

To complete the association, this endpoint validates the authentication data of the registered device.

```php
function patchRegisteredDevicesDeviceIdAssociations(
    string $deviceId,
    ?AssociationFinaliseRequest $body = null
): AssociationFinaliseResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `string` | Template, Required | The unique identifier of the SCA device that you are associating with a resource. |
| `body` | [`?AssociationFinaliseRequest`](../../doc/models/association-finalise-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`AssociationFinaliseResponse`](../../doc/models/association-finalise-response.md)

## Example Usage

```php
$deviceId = 'deviceId0';

$body = AssociationFinaliseRequestBuilder::init(
    [
        'ids7',
        'ids8',
        'ids9'
    ],
    AssociationDelegatedAuthenticationData1Builder::init(
        'sdkOutput4'
    )->build()
)->build();

$manageSCADevicesApi = $client->getManageSCADevicesApi();

try {
    $result = $manageSCADevicesApi->patchRegisteredDevicesDeviceIdAssociations(
        $deviceId,
        $body
    );
    echo 'AssociationFinaliseResponse:';
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


# Delete-Registered Devices-Id

Deletes an SCA device from the list of registered devices of a specific payment instrument.

```php
function deleteRegisteredDevicesId(string $id, string $paymentInstrumentId): void
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the SCA device. |
| `paymentInstrumentId` | `string` | Query, Required | The unique identifier of the payment instrument linked to the SCA device. |

## Response Type

**204**: No Content - look at the actual response code for the status of the request.

`void`

## Example Usage

```php
$id = 'id0';

$paymentInstrumentId = 'paymentInstrumentId2';

$manageSCADevicesApi = $client->getManageSCADevicesApi();

try {
    $manageSCADevicesApi->deleteRegisteredDevicesId(
        $id,
        $paymentInstrumentId
    );
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


# Patch-Registered Devices-Id

Completes the registration of an SCA device by validating the authentication data of the device. You can register SCA devices for [business accounts](https://docs.adyen.com/platforms/business-accounts/sca) or [Adyen-issued cards](https://docs.adyen.com/issuing/3d-secure/oob-auth-sdk).

```php
function patchRegisteredDevicesId(string $id, ?RegisterSCARequest $body = null): RegisterSCAFinalResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the SCA device. You obtain this `id` in the response of a POST&nbsp;[/registeredDevices](https://docs.adyen.com/api-explorer/balanceplatform/2/post/registeredDevices#responses-200-id) request. |
| `body` | [`?RegisterSCARequest`](../../doc/models/register-sca-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`RegisterSCAFinalResponse`](../../doc/models/register-sca-final-response.md)

## Example Usage

```php
$id = 'id0';

$manageSCADevicesApi = $client->getManageSCADevicesApi();

try {
    $result = $manageSCADevicesApi->patchRegisteredDevicesId($id);
    echo 'RegisterSCAFinalResponse:';
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

