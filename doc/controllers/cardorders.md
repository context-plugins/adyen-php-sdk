# Cardorders

```php
$cardordersApi = $client->getCardordersApi();
```

## Class Name

`CardordersApi`

## Methods

* [Get-Cardorders](../../doc/controllers/cardorders.md#get-cardorders)
* [Get-Cardorders-Id-Items](../../doc/controllers/cardorders.md#get-cardorders-id-items)


# Get-Cardorders

Returns a paginated list of card orders.

```php
function getCardorders(
    ?string $id = null,
    ?string $cardManufacturingProfileId = null,
    ?string $status = null,
    ?string $txVariantCode = null,
    ?\DateTime $createdSince = null,
    ?\DateTime $createdUntil = null,
    ?\DateTime $lockedSince = null,
    ?\DateTime $lockedUntil = null,
    ?string $serviceCenter = null,
    ?int $offset = null,
    ?int $limit = null
): PaginatedGetCardOrderResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `?string` | Query, Optional | The unique identifier of the card order. |
| `cardManufacturingProfileId` | `?string` | Query, Optional | The unique identifier of the card manufacturer profile. |
| `status` | `?string` | Query, Optional | The status of the card order. |
| `txVariantCode` | `?string` | Query, Optional | The unique code of the card manufacturer profile.<br><br>Possible values: **mcmaestro**, **mc**, **visa**, **mcdebit**. |
| `createdSince` | `?DateTime` | Query, Optional | Only include card orders that have been created on or after this point in time. The value must be in ISO 8601 format. For example, **2021-05-30T15:07:40Z**. |
| `createdUntil` | `?DateTime` | Query, Optional | Only include card orders that have been created on or before this point in time. The value must be in ISO 8601 format. For example, **2021-05-30T15:07:40Z**. |
| `lockedSince` | `?DateTime` | Query, Optional | Only include card orders that have been locked on or after this point in time. The value must be in ISO 8601 format. For example, **2021-05-30T15:07:40Z**. |
| `lockedUntil` | `?DateTime` | Query, Optional | Only include card orders that have been locked on or before this point in time. The value must be in ISO 8601 format. For example, **2021-05-30T15:07:40Z**. |
| `serviceCenter` | `?string` | Query, Optional | The service center at which the card is issued. The value is case-sensitive. |
| `offset` | `?int` | Query, Optional | Specifies the position of an element in a list of card orders. The response includes a list of card orders that starts at the specified offset.<br><br>**Default:** 0, which means that the response contains all the elements in the list of card orders. |
| `limit` | `?int` | Query, Optional | The number of card orders returned per page. **Default:** 10. |

## Response Type

**200**: OK - the request has succeeded.

[`PaginatedGetCardOrderResponse`](../../doc/models/paginated-get-card-order-response.md)

## Example Usage

```php
$cardOrdersApi = $client->getCardOrdersApi();

try {
    $result = $cardOrdersApi->getCardorders();
    echo 'PaginatedGetCardOrderResponse:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "cardOrders": [
    {
      "beginDate": "2022-12-05T00:00:00+01:00",
      "cardManufacturingProfileId": "UNIQUE_CARD_MANUFACTURER_PROFILE_ID",
      "endDate": "2022-12-06T00:00:00+01:00",
      "id": "UNIQUE_CARD_ORDER_ID",
      "lockDate": "2023-04-14T16:43:02+02:00",
      "serviceCenter": "IDEMIA Sittard",
      "status": "closed"
    }
  ],
  "hasNext": true,
  "hasPrevious": false
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |


# Get-Cardorders-Id-Items

Returns the item list of a specific card order.

```php
function getCardordersIdItems(
    string $id,
    ?int $offset = null,
    ?int $limit = null
): PaginatedGetCardOrderItemResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the card order. |
| `offset` | `?int` | Query, Optional | Specifies the position of an element in a list of card orders. The response includes a list of card order items that starts at the specified offset.<br><br>**Default:** 0, which means that the response contains all the elements in the list of card order items. |
| `limit` | `?int` | Query, Optional | The number of card order items returned per page. **Default:** 10. |

## Response Type

**200**: OK - the request has succeeded.

[`PaginatedGetCardOrderItemResponse`](../../doc/models/paginated-get-card-order-item-response.md)

## Example Usage

```php
$id = 'id0';

$cardOrdersApi = $client->getCardOrdersApi();

try {
    $result = $cardOrdersApi->getCardordersIdItems($id);
    echo 'PaginatedGetCardOrderItemResponse:';
    var_dump($result);
} catch (RestServiceErrorException $exp) {
    echo 'Caught RestServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "data": [
    {
      "card": {
        "status": "shipped"
      },
      "cardOrderItemId": "UNIQUE_CARD_ORDER_ITEM_ID",
      "paymentInstrumentId": "UNIQUE_PAYMENT_INSTRUMENT_ID",
      "pin": {
        "status": "produced"
      },
      "shippingMethod": "Cardholder Post Basic National"
    }
  ],
  "hasNext": false,
  "hasPrevious": false
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - authentication required. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`RestServiceErrorException`](../../doc/models/rest-service-error-exception.md) |

