# Transactionrules

```php
$transactionrulesApi = $client->getTransactionrulesApi();
```

## Class Name

`TransactionrulesApi`

## Methods

* [Post-Transaction Rules](../../doc/controllers/transactionrules.md#post-transaction-rules)
* [Get-Transaction Rules-Transaction Rule Id](../../doc/controllers/transactionrules.md#get-transaction-rules-transaction-rule-id)
* [Delete-Transaction Rules-Transaction Rule Id](../../doc/controllers/transactionrules.md#delete-transaction-rules-transaction-rule-id)
* [Patch-Transaction Rules-Transaction Rule Id](../../doc/controllers/transactionrules.md#patch-transaction-rules-transaction-rule-id)


# Post-Transaction Rules

Creates a [transaction rule](https://docs.adyen.com/issuing/transaction-rules). When your user makes a transaction with their Adyen-issued card, the transaction is allowed or declined based on the conditions and outcome defined in the transaction rule. You can apply the transaction rule to several cards, such as all the cards in your platform, or to a specific card. For use cases, see [examples](https://docs.adyen.com/issuing/transaction-rules/examples).

```php
function postTransactionRules(?TransactionRuleInfo $body = null): TransactionRule
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?TransactionRuleInfo`](../../doc/models/transaction-rule-info.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`TransactionRule`](../../doc/models/transaction-rule.md)

## Example Usage

```php
$body = TransactionRuleInfoBuilder::init(
    'Allow only point-of-sale transactions',
    TransactionRuleEntityKey2Builder::init()
        ->entityReference('PI3227C223222B5FG88SB8BHR')
        ->entityType('paymentInstrument')
        ->build(),
    TransactionRuleInterval1Builder::init(
        Type131Enum::PERTRANSACTION
    )->build(),
    'YOUR_REFERENCE_4F7346',
    TransactionRuleRestrictions1Builder::init()
        ->processingTypes(
            ProcessingTypesRestriction1Builder::init(
                'noneMatch'
            )
                ->value(
                    [
                        Value4Enum::POS
                    ]
                )
                ->build()
        )
        ->build(),
    Type141Enum::BLOCKLIST
)
    ->status(Status6Enum::ACTIVE)
    ->build();

$transactionRulesApi = $client->getTransactionRulesApi();

try {
    $result = $transactionRulesApi->postTransactionRules($body);
    echo 'TransactionRule:';
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
  "description": "Allow only point-of-sale transactions",
  "entityKey": {
    "entityReference": "PI3227C223222B5FG88SB8BHR",
    "entityType": "paymentInstrument"
  },
  "interval": {
    "timeZone": "UTC",
    "type": "perTransaction"
  },
  "outcomeType": "hardBlock",
  "reference": "YOUR_REFERENCE_4F7346",
  "requestType": "authorization",
  "ruleRestrictions": {
    "processingTypes": {
      "operation": "noneMatch",
      "value": [
        "pos"
      ]
    }
  },
  "startDate": "2023-06-29T22:34:36.173226192+02:00",
  "status": "active",
  "type": "blockList",
  "id": "TR3227C223222H5J4D9ML9V4D"
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


# Get-Transaction Rules-Transaction Rule Id

Returns the details of a transaction rule.

```php
function getTransactionRulesTransactionRuleId(string $transactionRuleId): TransactionRuleResponse
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionRuleId` | `string` | Template, Required | The unique identifier of the transaction rule. |

## Response Type

**200**: OK - the request has succeeded.

[`TransactionRuleResponse`](../../doc/models/transaction-rule-response.md)

## Example Usage

```php
$transactionRuleId = 'transactionRuleId2';

$transactionRulesApi = $client->getTransactionRulesApi();

try {
    $result = $transactionRulesApi->getTransactionRulesTransactionRuleId($transactionRuleId);
    echo 'TransactionRuleResponse:';
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
  "transactionRule": {
    "description": "Only allow point-of-sale transactions",
    "entityKey": {
      "entityReference": "PI3227C223222B5FN65FN5NS9",
      "entityType": "paymentInstrument"
    },
    "interval": {
      "timeZone": "UTC",
      "type": "perTransaction"
    },
    "outcomeType": "hardBlock",
    "reference": "YOUR_REFERENCE_4F7346",
    "requestType": "authorization",
    "ruleRestrictions": {
      "processingTypes": {
        "operation": "noneMatch",
        "value": [
          "pos"
        ]
      }
    },
    "startDate": "2022-08-02T16:07:00.851374+02:00",
    "status": "active",
    "type": "blockList",
    "id": "TR32272223222B5GFSGFLFCHM"
  }
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


# Delete-Transaction Rules-Transaction Rule Id

Deletes a transaction rule.

```php
function deleteTransactionRulesTransactionRuleId(string $transactionRuleId): TransactionRule
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionRuleId` | `string` | Template, Required | The unique identifier of the transaction rule. |

## Response Type

**200**: OK - the request has succeeded.

[`TransactionRule`](../../doc/models/transaction-rule.md)

## Example Usage

```php
$transactionRuleId = 'transactionRuleId2';

$transactionRulesApi = $client->getTransactionRulesApi();

try {
    $result = $transactionRulesApi->deleteTransactionRulesTransactionRuleId($transactionRuleId);
    echo 'TransactionRule:';
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
  "type": "velocity",
  "id": "TR3227C223222C5GXT3DD5VCF"
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


# Patch-Transaction Rules-Transaction Rule Id

Updates a transaction rule.

* To update only the status of a transaction rule, send only the `status` parameter. All other parameters not provided in the request are left unchanged.

* When updating any other parameter, you need to send all existing resource parameters. If you omit a parameter in the request, that parameter is removed from the resource.

```php
function patchTransactionRulesTransactionRuleId(
    string $transactionRuleId,
    ?TransactionRuleInfo $body = null
): TransactionRule
```

## Authentication

This endpoint requires [clientKey](../../doc/auth/custom-query-parameter.md) **OR** [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionRuleId` | `string` | Template, Required | The unique identifier of the transaction rule. |
| `body` | [`?TransactionRuleInfo`](../../doc/models/transaction-rule-info.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`TransactionRule`](../../doc/models/transaction-rule.md)

## Example Usage

```php
$transactionRuleId = 'transactionRuleId2';

$body = TransactionRuleInfoBuilder::init(
    'Allow only point-of-sale transactions',
    TransactionRuleEntityKey2Builder::init()
        ->entityReference('PI3227C223222B5FG88SB8BHR')
        ->entityType('paymentInstrument')
        ->build(),
    TransactionRuleInterval1Builder::init(
        Type131Enum::WEEKLY
    )->build(),
    'YOUR_REFERENCE_4F7346',
    TransactionRuleRestrictions1Builder::init()
        ->processingTypes(
            ProcessingTypesRestriction1Builder::init(
                'noneMatch'
            )
                ->value(
                    [
                        Value4Enum::POS
                    ]
                )
                ->build()
        )
        ->build(),
    Type141Enum::BLOCKLIST
)
    ->status(Status6Enum::INACTIVE)
    ->build();

$transactionRulesApi = $client->getTransactionRulesApi();

try {
    $result = $transactionRulesApi->patchTransactionRulesTransactionRuleId(
        $transactionRuleId,
        $body
    );
    echo 'TransactionRule:';
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
  "startDate": "2022-11-17T00:07:09.10057663+01:00",
  "status": "inactive",
  "type": "velocity",
  "id": "TR3227C223222C5GXR3XP596N"
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

