# SC Aassociationmanagement

```php
$sCAassociationmanagementApi = $client->getSCAassociationmanagementApi();
```

## Class Name

`SCAassociationmanagementApi`

## Methods

* [Get-Sca Associations](../../doc/controllers/sc-aassociationmanagement.md#get-sca-associations)
* [Delete-Sca Associations](../../doc/controllers/sc-aassociationmanagement.md#delete-sca-associations)
* [Patch-Sca Associations](../../doc/controllers/sc-aassociationmanagement.md#patch-sca-associations)


# Get-Sca Associations

Returns a paginated list of the SCA devices associated with a specific entity.

:information_source: **Note** This endpoint does not require authentication.

```php
function getScaAssociations(
    string $entityType,
    string $entityId,
    int $pageSize,
    int $pageNumber
): ListAssociationsResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `entityType` | [`string(ScaEntityTypeEnum)`](../../doc/models/sca-entity-type-enum.md) | Query, Required | The type of entity you want to retrieve a list of associations for.<br><br>Possible values: **accountHolder**, **legalEntity** or **paymentInstrument**. |
| `entityId` | `string` | Query, Required | The unique identifier of the entity.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100` |
| `pageSize` | `int` | Query, Required | The number of items to have on a page.<br><br>Default: **5**.<br><br>**Constraints**: `>= 1`, `<= 10` |
| `pageNumber` | `int` | Query, Required | The index of the page to retrieve. The index of the first page is **0** (zero).<br><br>Default:  **0**. |

## Response Type

**200**: OK - The request has succeeded.

[`ListAssociationsResponse`](../../doc/models/list-associations-response.md)

## Example Usage

```php
$entityType = ScaEntityTypeEnum::ACCOUNTHOLDER;

$entityId = 'entityId2';

$pageSize = 10;

$pageNumber = 110;

$sCAAssociationManagementApi = $client->getSCAAssociationManagementApi();

try {
    $result = $sCAAssociationManagementApi->getScaAssociations(
        $entityType,
        $entityId,
        $pageSize,
        $pageNumber
    );
    echo 'ListAssociationsResponse:';
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
  "_links": {
    "self": {
      "href": "https://exampledomain.com/bcl/api/v2/scaAssociations?pageNumber=0&entityType=accountHolder&pageSize=10&entityId=AH3227J223222D5HHM4779X6X"
    }
  },
  "itemsTotal": 2,
  "pagesTotal": 1,
  "data": [
    {
      "scaDeviceId": "BSDR11111111111A1AAA1AAAAA1AA1",
      "scaDeviceName": "Device 1",
      "scaDeviceType": "ios",
      "entityType": "accountHolder",
      "entityId": "AH00000000000000000000001",
      "status": "active",
      "createdAt": "2025-09-02T14:39:17.232Z"
    },
    {
      "scaDeviceId": "BSDR22222222222B2BBB2BBBBB2BB2",
      "scaDeviceName": "Device 2",
      "scaDeviceType": "ios",
      "entityType": "accountHolder",
      "entityId": "AH00000000000000000000001",
      "status": "pendingApproval",
      "createdAt": "2025-09-02T14:39:17.232Z"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request - The request contains invalid input and fails validation. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - The server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Sca Associations

Deletes one or more SCA associations for a device.

:information_source: **Note** This endpoint does not require authentication.

```php
function deleteScaAssociations(string $wWWAuthenticate, ?RemoveAssociationRequest $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `wWWAuthenticate` | `string` | Header, Required | The header for authenticating through SCA.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `20000` |
| `body` | [`?RemoveAssociationRequest`](../../doc/models/remove-association-request.md) | Body, Optional | - |

## Response Type

**204**: No Content - Successful association deletion.

`void`

## Example Usage

```php
$wWWAuthenticate = 'WWW-Authenticate2';

$body = RemoveAssociationRequestBuilder::init(
    'AH00000000000000000000001',
    ScaEntityType3Enum::ACCOUNTHOLDER,
    [
        'BSDR42XV3223223S5N6CDQDGH53M8H'
    ]
)->build();

$sCAAssociationManagementApi = $client->getSCAAssociationManagementApi();

try {
    $sCAAssociationManagementApi->deleteScaAssociations(
        $wWWAuthenticate,
        $body
    );
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - The server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Patch-Sca Associations

Approves a previously created association that is in a pending state.

:information_source: **Note** This endpoint does not require authentication.

```php
function patchScaAssociations(
    string $wWWAuthenticate,
    ?ApproveAssociationRequest $body = null
): ApproveAssociationResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `wWWAuthenticate` | `string` | Header, Required | The header for authenticating through SCA.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `20000` |
| `body` | [`?ApproveAssociationRequest`](../../doc/models/approve-association-request.md) | Body, Optional | - |

## Response Type

**200**: OK - Successful approval

[`ApproveAssociationResponse`](../../doc/models/approve-association-response.md)

## Example Usage

```php
$wWWAuthenticate = 'WWW-Authenticate2';

$body = ApproveAssociationRequestBuilder::init(
    'AH00000000000000000000001',
    ScaEntityType2Enum::ACCOUNTHOLDER,
    [
        'BSDR42XV3223223S5N6CDQDGH53M8H'
    ],
    AssociationStatus1Enum::ACTIVE
)->build();

$sCAAssociationManagementApi = $client->getSCAAssociationManagementApi();

try {
    $result = $sCAAssociationManagementApi->patchScaAssociations(
        $wWWAuthenticate,
        $body
    );
    echo 'ApproveAssociationResponse:';
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
      "scaDeviceId": "BSDR42XV3223223S5N6CDQDGH53M8H",
      "entityType": "accountHolder",
      "entityId": "AH00000000000000000000001",
      "status": "active"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - The server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

