# SC Adevicemanagement

```php
$sCAdevicemanagementApi = $client->getSCAdevicemanagementApi();
```

## Class Name

`SCAdevicemanagementApi`

## Methods

* [Post-Sca Devices](../../doc/controllers/sc-adevicemanagement.md#post-sca-devices)
* [Delete-Sca Devices-Device Id](../../doc/controllers/sc-adevicemanagement.md#delete-sca-devices-device-id)
* [Patch-Sca Devices-Device Id](../../doc/controllers/sc-adevicemanagement.md#patch-sca-devices-device-id)
* [Post-Sca Devices-Device Id-Sca Associations](../../doc/controllers/sc-adevicemanagement.md#post-sca-devices-device-id-sca-associations)


# Post-Sca Devices

Begins the registration process for a new Strong Customer Authentication (SCA) device.

:information_source: **Note** This endpoint does not require authentication.

```php
function postScaDevices(?BeginScaDeviceRegistrationRequest $body = null): BeginScaDeviceRegistrationResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?BeginScaDeviceRegistrationRequest`](../../doc/models/begin-sca-device-registration-request.md) | Body, Optional | - |

## Response Type

**201**: Created - A device resource is created. The initial step of registration is complete, but the device isn't ready for use.

[`BeginScaDeviceRegistrationResponse`](../../doc/models/begin-sca-device-registration-response.md)

## Example Usage

```php
$body = BeginScaDeviceRegistrationRequestBuilder::init(
    'My Device',
    'eyJjaGFsbGVuZ2UiOiJVWEZaTURONGNXWjZUVFExUlhWV2JuaEJPVzVzTm05cVVEUktUbFZtZGtrPSJ9'
)->build();

$sCADeviceManagementApi = $client->getSCADeviceManagementApi();

try {
    $result = $sCADeviceManagementApi->postScaDevices($body);
    echo 'BeginScaDeviceRegistrationResponse:';
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
  "scaDevice": {
    "id": "BSDR42XV3223223S5N6CDQDGH53M8H",
    "name": "My Device",
    "type": "ios"
  },
  "sdkInput": "eyJjaGFsbGVuZ2UiOiJVWEZaTURONGNXWjZUVFExUlhWV2JuaEJPVzVzTm05cVVEUktUbFZtZGtrPSJ9"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request contains invalid input and fails validation. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - The server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Sca Devices-Device Id

Deletes a Strong Customer Authentication (SCA) device.

:information_source: **Note** This endpoint does not require authentication.

```php
function deleteScaDevicesDeviceId(string $deviceId): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `string` | Template, Required | The unique identifier of the SCA device to delete.<br><br>**Constraints**: *Minimum Length*: `30`, *Maximum Length*: `30` |

## Response Type

**204**: No Content - The device was deleted successfully.

`void`

## Example Usage

```php
$deviceId = 'deviceId0';

$sCADeviceManagementApi = $client->getSCADeviceManagementApi();

try {
    $sCADeviceManagementApi->deleteScaDevicesDeviceId($deviceId);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request contains invalid input and fails validation. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - Device not found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - The server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Patch-Sca Devices-Device Id

Finishes the registration process for a new Strong Customer Authentication (SCA) device.

:information_source: **Note** This endpoint does not require authentication.

```php
function patchScaDevicesDeviceId(
    string $deviceId,
    ?FinishScaDeviceRegistrationRequest $body = null
): FinishScaDeviceRegistrationResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `string` | Template, Required | The unique identifier of the SCA device that you are associating with a resource.<br><br>**Constraints**: *Minimum Length*: `30`, *Maximum Length*: `30` |
| `body` | [`?FinishScaDeviceRegistrationRequest`](../../doc/models/finish-sca-device-registration-request.md) | Body, Optional | - |

## Response Type

**200**: OK - Device registration was completed successfully.

[`FinishScaDeviceRegistrationResponse`](../../doc/models/finish-sca-device-registration-response.md)

## Example Usage

```php
$deviceId = 'deviceId0';

$body = FinishScaDeviceRegistrationRequestBuilder::init(
    'eyJjaGFsbGVuZ2UiOiJVWEZaTURONGNXWjZUVFExUlhWV2JuaEJPVzVzTm05cVVEUktUbFZtZGtrPSJ9'
)->build();

$sCADeviceManagementApi = $client->getSCADeviceManagementApi();

try {
    $result = $sCADeviceManagementApi->patchScaDevicesDeviceId(
        $deviceId,
        $body
    );
    echo 'FinishScaDeviceRegistrationResponse:';
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
  "scaDevice": {
    "id": "BSDR42XV3223223S5N6CDQDGH53M8H",
    "name": "Device",
    "type": "ios"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request contains invalid input and fails validation. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - Device not found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - The server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Sca Devices-Device Id-Sca Associations

Creates an association between an SCA-enabled device and an entity, such as an account holder. This action does not guarantee the association is immediately ready for use; its status may be `pendingApproval` if the account holder has existing devices.

:information_source: **Note** This endpoint does not require authentication.

```php
function postScaDevicesDeviceIdScaAssociations(
    string $deviceId,
    ?SubmitScaAssociationRequest $body = null
): SubmitScaAssociationResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `deviceId` | `string` | Template, Required | The unique identifier of the SCA device that you are associating with a resource.<br><br>**Constraints**: *Minimum Length*: `30`, *Maximum Length*: `30` |
| `body` | [`?SubmitScaAssociationRequest`](../../doc/models/submit-sca-association-request.md) | Body, Optional | - |

## Response Type

**201**: Created - Association created.

[`SubmitScaAssociationResponse`](../../doc/models/submit-sca-association-response.md)

## Example Usage

```php
$deviceId = 'deviceId0';

$body = SubmitScaAssociationRequestBuilder::init(
    [
        ScaEntityBuilder::init(
            'AH00000000000000000000001',
            ScaEntityType4Enum::ACCOUNTHOLDER
        )->build()
    ]
)->build();

$sCADeviceManagementApi = $client->getSCADeviceManagementApi();

try {
    $result = $sCADeviceManagementApi->postScaDevicesDeviceIdScaAssociations(
        $deviceId,
        $body
    );
    echo 'SubmitScaAssociationResponse:';
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
  "scaAssociations": [
    {
      "scaDeviceId": "BSDR11111111111A1AAA1AAAAA1AA1",
      "entityType": "accountHolder",
      "entityId": "AH00000000000000000000001",
      "status": "pendingApproval"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request contains invalid input and fails validation. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - Device not found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - The server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

