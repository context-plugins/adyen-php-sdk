# Paymentinstrumentgroups

```php
$paymentinstrumentgroupsApi = $client->getPaymentinstrumentgroupsApi();
```

## Class Name

`PaymentinstrumentgroupsApi`

## Methods

* [Post-Payment Instrument Groups](../../doc/controllers/paymentinstrumentgroups.md#post-payment-instrument-groups)
* [Get-Payment Instrument Groups-Id](../../doc/controllers/paymentinstrumentgroups.md#get-payment-instrument-groups-id)
* [Get-Payment Instrument Groups-Id-Transaction Rules](../../doc/controllers/paymentinstrumentgroups.md#get-payment-instrument-groups-id-transaction-rules)


# Post-Payment Instrument Groups

Creates a payment instrument group to associate and group payment instrument resources together. You can apply a transaction rule to a payment instrument group.

```php
function postPaymentInstrumentGroups(?PaymentInstrumentGroupInfo $body = null): PaymentInstrumentGroup
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?PaymentInstrumentGroupInfo`](../../doc/models/payment-instrument-group-info.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`PaymentInstrumentGroup`](../../doc/models/payment-instrument-group.md)

## Example Usage

```php
$body = PaymentInstrumentGroupInfoBuilder::init(
    'YOUR_BALANCE_PLATFORM',
    'mc'
)->build();

$paymentInstrumentGroupsApi = $client->getPaymentInstrumentGroupsApi();

try {
    $result = $paymentInstrumentGroupsApi->postPaymentInstrumentGroups($body);
    echo 'PaymentInstrumentGroup:';
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
  "balancePlatform": "YOUR_BALANCE_PLATFORM",
  "txVariant": "mc",
  "id": "PG32272223222H5J4DCRVC9DH"
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


# Get-Payment Instrument Groups-Id

Returns the details of a payment instrument group.

```php
function getPaymentInstrumentGroupsId(string $id): PaymentInstrumentGroup
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the payment instrument group. |

## Response Type

**200**: OK - the request has succeeded.

[`PaymentInstrumentGroup`](../../doc/models/payment-instrument-group.md)

## Example Usage

```php
$id = 'id0';

$paymentInstrumentGroupsApi = $client->getPaymentInstrumentGroupsApi();

try {
    $result = $paymentInstrumentGroupsApi->getPaymentInstrumentGroupsId($id);
    echo 'PaymentInstrumentGroup:';
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
  "balancePlatform": "YOUR_BALANCE_PLATFORM",
  "txVariant": "mc",
  "id": "PG3227C223222B5CMD3FJFKGZ"
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


# Get-Payment Instrument Groups-Id-Transaction Rules

Returns a list of all the transaction rules associated with a payment instrument group.

```php
function getPaymentInstrumentGroupsIdTransactionRules(string $id): TransactionRulesResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The unique identifier of the payment instrument group. |

## Response Type

**200**: OK - the request has succeeded.

[`TransactionRulesResponse`](../../doc/models/transaction-rules-response.md)

## Example Usage

```php
$id = 'id0';

$paymentInstrumentGroupsApi = $client->getPaymentInstrumentGroupsApi();

try {
    $result = $paymentInstrumentGroupsApi->getPaymentInstrumentGroupsIdTransactionRules($id);
    echo 'TransactionRulesResponse:';
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
  "transactionRules": [
    {
      "aggregationLevel": "paymentInstrument",
      "description": "Up to 1000 EUR per card for the last 12 hours",
      "entityKey": {
        "entityReference": "PG3227C223222C5GXR3M5592Q",
        "entityType": "paymentInstrumentGroup"
      },
      "interval": {
        "duration": {
          "unit": "hours",
          "value": 12
        },
        "timeZone": "UTC",
        "type": "sliding"
      },
      "outcomeType": "hardBlock",
      "reference": "YOUR_REFERENCE_2918A",
      "requestType": "authorization",
      "ruleRestrictions": {
        "totalAmount": {
          "operation": "greaterThan",
          "value": {
            "currency": "EUR",
            "value": 100000
          }
        }
      },
      "status": "inactive",
      "type": "velocity",
      "id": "TR3227C223222C5GXR3XP596N"
    },
    {
      "aggregationLevel": "paymentInstrument",
      "description": "NL only",
      "entityKey": {
        "entityReference": "PG3227C223222C5GXR3M5592Q",
        "entityType": "paymentInstrumentGroup"
      },
      "interval": {
        "duration": {
          "unit": "hours",
          "value": 12
        },
        "timeZone": "UTC",
        "type": "sliding"
      },
      "outcomeType": "hardBlock",
      "reference": "myRule12345",
      "requestType": "authorization",
      "ruleRestrictions": {
        "totalAmount": {
          "operation": "greaterThan",
          "value": {
            "currency": "EUR",
            "value": 100000
          }
        }
      },
      "status": "inactive",
      "type": "velocity",
      "id": "TR3227C223222C5GXR3WC595H"
    }
  ]
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

