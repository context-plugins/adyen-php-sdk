# Splitconfiguration-Merchantlevel

```php
$splitconfigurationMerchantlevelApi = $client->getSplitconfigurationMerchantlevelApi();
```

## Class Name

`SplitconfigurationMerchantlevelApi`

## Methods

* [Get-Merchants-Merchant Id-Split Configurations](../../doc/controllers/splitconfiguration-merchantlevel.md#get-merchants-merchant-id-split-configurations)
* [Post-Merchants-Merchant Id-Split Configurations](../../doc/controllers/splitconfiguration-merchantlevel.md#post-merchants-merchant-id-split-configurations)
* [Get-Merchants-Merchant Id-Split Configurations-Split Configuration Id](../../doc/controllers/splitconfiguration-merchantlevel.md#get-merchants-merchant-id-split-configurations-split-configuration-id)
* [Post-Merchants-Merchant Id-Split Configurations-Split Configuration Id](../../doc/controllers/splitconfiguration-merchantlevel.md#post-merchants-merchant-id-split-configurations-split-configuration-id)
* [Delete-Merchants-Merchant Id-Split Configurations-Split Configuration Id](../../doc/controllers/splitconfiguration-merchantlevel.md#delete-merchants-merchant-id-split-configurations-split-configuration-id)
* [Patch-Merchants-Merchant Id-Split Configurations-Split Configuration Id](../../doc/controllers/splitconfiguration-merchantlevel.md#patch-merchants-merchant-id-split-configurations-split-configuration-id)
* [Delete-Merchants-Merchant Id-Split Configurations-Split Configuration Id-Rules-Rule Id](../../doc/controllers/splitconfiguration-merchantlevel.md#delete-merchants-merchant-id-split-configurations-split-configuration-id-rules-rule-id)
* [Patch-Merchants-Merchant Id-Split Configurations-Split Configuration Id-Rules-Rule Id](../../doc/controllers/splitconfiguration-merchantlevel.md#patch-merchants-merchant-id-split-configurations-split-configuration-id-rules-rule-id)
* [Patch-Merchants-Split Configurations-Rules-Split Logic](../../doc/controllers/splitconfiguration-merchantlevel.md#patch-merchants-split-configurations-rules-split-logic)


# Get-Merchants-Merchant Id-Split Configurations

Returns the list of split configuration profiles for the merchant account.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function getMerchantsMerchantIdSplitConfigurations(string $merchantId): SplitConfigurationList
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfigurationList`](../../doc/models/split-configuration-list.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->getMerchantsMerchantIdSplitConfigurations($merchantId);
    echo 'SplitConfigurationList:';
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
      "description": "Your description for the split configuration",
      "rules": [
        {
          "currency": "GBP",
          "fundingSource": "ANY",
          "paymentMethod": "ANY",
          "ruleId": "SCRL4224P22322585HP89PPCST6BCZ",
          "shopperInteraction": "ANY",
          "splitLogic": {
            "additionalCommission": {
              "fixedAmount": 100,
              "variablePercentage": 100,
              "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
            },
            "chargeback": "deductFromLiableAccount",
            "commission": {
              "fixedAmount": 200,
              "variablePercentage": 100
            },
            "splitLogicId": "SCLG4224P22322585HP89PPCSV27VP",
            "paymentFee": "deductFromLiableAccount",
            "remainder": "addToOneBalanceAccount",
            "tip": "addToOneBalanceAccount"
          }
        }
      ],
      "splitConfigurationId": "SCNF4224P22322585HP89PPCSS24MF"
    },
    {
      "description": "Your description for the second split configuration",
      "rules": [
        {
          "currency": "ANY",
          "fundingSource": "ANY",
          "paymentMethod": "ANY",
          "ruleId": "SCRL4224P22322585HPCX384JW65VW",
          "shopperInteraction": "ANY",
          "splitLogic": {
            "additionalCommission": {
              "fixedAmount": 10,
              "variablePercentage": 50,
              "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
            },
            "chargeback": "deductFromLiableAccount",
            "commission": {
              "fixedAmount": 10,
              "variablePercentage": 100
            },
            "splitLogicId": "SCLG4224P22322585HPCX384JX52M2",
            "paymentFee": "deductFromLiableAccount",
            "remainder": "addToOneBalanceAccount",
            "tip": "addToOneBalanceAccount"
          }
        },
        {
          "currency": "EUR",
          "fundingSource": "ANY",
          "paymentMethod": "visa",
          "ruleId": "SCRL4224P22322585HPCX5V4KV6L2R",
          "shopperInteraction": "ANY",
          "splitLogic": {
            "additionalCommission": {
              "fixedAmount": 100,
              "variablePercentage": 0,
              "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
            },
            "chargeback": "deductFromLiableAccount",
            "commission": {
              "fixedAmount": 100,
              "variablePercentage": 100
            },
            "splitLogicId": "SCLG4224P22322585HPCX5V4KW26C9",
            "paymentFee": "deductFromLiableAccount",
            "remainder": "addToLiableAccount",
            "tip": "addToLiableAccount"
          }
        }
      ],
      "splitConfigurationId": "SCNF4224P22322585HPCX384JV6JGX"
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


# Post-Merchants-Merchant Id-Split Configurations

Creates a split configuration profile to [split payments automatically](https://docs.adyen.com/platforms/automatic-split-configuration/). After you [associate it with a store](https://docs.adyen.com/api-explorer/Management/latest/patch/merchants/(merchantId)/stores/(storeId)#request-splitConfiguration) in your merchant account, it splits the funds of all transactions processed through that store between your liable balance account and [your user's balance account](https://docs.adyen.com/api-explorer/Management/latest/patch/merchants/(merchantId)/stores/(storeId)#request-splitConfiguration-balanceAccountId).

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function postMerchantsMerchantIdSplitConfigurations(
    string $merchantId,
    ?SplitConfiguration $body = null
): SplitConfiguration
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `body` | [`?SplitConfiguration`](../../doc/models/split-configuration.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfiguration`](../../doc/models/split-configuration.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$body = SplitConfigurationBuilder::init(
    'Your description for the split configuration',
    [
        SplitConfigurationRuleBuilder::init(
            'ANY',
            FundingSource1Enum::ANY,
            'ANY',
            ShopperInteraction11Enum::ANY,
            SplitConfigurationLogic2Builder::init(
                Commission1Builder::init()
                    ->fixedAmount(10)
                    ->variablePercentage(100)
                    ->build()
            )
                ->additionalCommission(
                    AdditionalCommission1Builder::init()
                        ->balanceAccountId('BA3227C223222H5HQ2XX77VVH')
                        ->fixedAmount(10)
                        ->variablePercentage(50)
                        ->build()
                )
                ->chargeback(BehaviorEnum::DEDUCTFROMLIABLEACCOUNT)
                ->paymentFee(PaymentFeeEnum::DEDUCTFROMLIABLEACCOUNT)
                ->remainder(RemainderEnum::ADDTOONEBALANCEACCOUNT)
                ->tip(TipEnum::ADDTOONEBALANCEACCOUNT)
                ->build()
        )->build()
    ]
)->build();

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->postMerchantsMerchantIdSplitConfigurations(
        $merchantId,
        $body
    );
    echo 'SplitConfiguration:';
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
  "description": "Your description for the split configuration",
  "rules": [
    {
      "currency": "ANY",
      "fundingSource": "ANY",
      "paymentMethod": "ANY",
      "ruleId": "SCRL4224P22322585HPCX384JW65VW",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 10,
          "variablePercentage": 50,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 10,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX384JX52M2",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToOneBalanceAccount",
        "tip": "addToOneBalanceAccount"
      }
    }
  ],
  "splitConfigurationId": "SCNF4224P22322585HPCX384JV6JGX"
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


# Get-Merchants-Merchant Id-Split Configurations-Split Configuration Id

Returns the details of the split configuration profile specified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function getMerchantsMerchantIdSplitConfigurationsSplitConfigurationId(
    string $merchantId,
    string $splitConfigurationId
): SplitConfiguration
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `splitConfigurationId` | `string` | Template, Required | The unique identifier of the split configuration. |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfiguration`](../../doc/models/split-configuration.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$splitConfigurationId = 'splitConfigurationId4';

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->getMerchantsMerchantIdSplitConfigurationsSplitConfigurationId(
        $merchantId,
        $splitConfigurationId
    );
    echo 'SplitConfiguration:';
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
  "description": "Your description for the split configuration",
  "rules": [
    {
      "currency": "ANY",
      "fundingSource": "ANY",
      "paymentMethod": "ANY",
      "ruleId": "SCRL4224P22322585HPCX384JW65VW",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 10,
          "variablePercentage": 50,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 10,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX384JX52M2",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToOneBalanceAccount",
        "tip": "addToOneBalanceAccount"
      }
    },
    {
      "currency": "EUR",
      "fundingSource": "ANY",
      "paymentMethod": "visa",
      "ruleId": "SCRL4224P22322585HPCX5V4KV6L2R",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 100,
          "variablePercentage": 0,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 100,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX5V4KW26C9",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToLiableAccount",
        "tip": "addToLiableAccount"
      }
    }
  ],
  "splitConfigurationId": "SCNF4224P22322585HPCX384JV6JGX"
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


# Post-Merchants-Merchant Id-Split Configurations-Split Configuration Id

[Creates a rule](https://docs.adyen.com/platforms/automatic-split-configuration/manage-split-configurations/api/#create-rule) in the split configuration profile specified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function postMerchantsMerchantIdSplitConfigurationsSplitConfigurationId(
    string $merchantId,
    string $splitConfigurationId,
    ?SplitConfigurationRule $body = null
): SplitConfiguration
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `splitConfigurationId` | `string` | Template, Required | The unique identifier of the split configuration. |
| `body` | [`?SplitConfigurationRule`](../../doc/models/split-configuration-rule.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfiguration`](../../doc/models/split-configuration.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$splitConfigurationId = 'splitConfigurationId4';

$body = SplitConfigurationRuleBuilder::init(
    'USD',
    FundingSource1Enum::ANY,
    'visa',
    ShopperInteraction11Enum::POS,
    SplitConfigurationLogic2Builder::init(
        Commission1Builder::init()
            ->fixedAmount(10)
            ->variablePercentage(100)
            ->build()
    )
        ->additionalCommission(
            AdditionalCommission1Builder::init()
                ->balanceAccountId('BA3227C223222H5HQ2XX77VVH')
                ->fixedAmount(10)
                ->variablePercentage(50)
                ->build()
        )
        ->chargeback(BehaviorEnum::DEDUCTFROMLIABLEACCOUNT)
        ->paymentFee(PaymentFeeEnum::DEDUCTFROMLIABLEACCOUNT)
        ->remainder(RemainderEnum::ADDTOLIABLEACCOUNT)
        ->tip(TipEnum::ADDTOONEBALANCEACCOUNT)
        ->build()
)->build();

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->postMerchantsMerchantIdSplitConfigurationsSplitConfigurationId(
        $merchantId,
        $splitConfigurationId,
        $body
    );
    echo 'SplitConfiguration:';
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
  "description": "My first split configuration",
  "rules": [
    {
      "currency": "ANY",
      "fundingSource": "ANY",
      "paymentMethod": "ANY",
      "ruleId": "SCRL4224P22322585HPCX384JW65VW",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 10,
          "variablePercentage": 50,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 10,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX384JX52M2",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToOneBalanceAccount",
        "tip": "addToOneBalanceAccount"
      }
    },
    {
      "currency": "USD",
      "fundingSource": "ANY",
      "paymentMethod": "visa",
      "ruleId": "SCRL4224P22322585HPCX5V4KV6L2R",
      "shopperInteraction": "POS",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 10,
          "variablePercentage": 50,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 10,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX5V4KW26C9",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToLiableAccount",
        "tip": "addToOneBalanceAccount"
      }
    }
  ],
  "splitConfigurationId": "SCNF4224P22322585HPCX384JV6JGX"
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


# Delete-Merchants-Merchant Id-Split Configurations-Split Configuration Id

Deletes the split configuration profile specified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function deleteMerchantsMerchantIdSplitConfigurationsSplitConfigurationId(
    string $merchantId,
    string $splitConfigurationId
): SplitConfiguration
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `splitConfigurationId` | `string` | Template, Required | The unique identifier of the split configuration. |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfiguration`](../../doc/models/split-configuration.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$splitConfigurationId = 'splitConfigurationId4';

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->deleteMerchantsMerchantIdSplitConfigurationsSplitConfigurationId(
        $merchantId,
        $splitConfigurationId
    );
    echo 'SplitConfiguration:';
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


# Patch-Merchants-Merchant Id-Split Configurations-Split Configuration Id

Changes the description of the split configuration profile specified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function patchMerchantsMerchantIdSplitConfigurationsSplitConfigurationId(
    string $merchantId,
    string $splitConfigurationId,
    ?UpdateSplitConfigurationRequest $body = null
): SplitConfiguration
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `splitConfigurationId` | `string` | Template, Required | The unique identifier of the split configuration. |
| `body` | [`?UpdateSplitConfigurationRequest`](../../doc/models/update-split-configuration-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfiguration`](../../doc/models/split-configuration.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$splitConfigurationId = 'splitConfigurationId4';

$body = UpdateSplitConfigurationRequestBuilder::init(
    'Updated description for the split configuration'
)->build();

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->patchMerchantsMerchantIdSplitConfigurationsSplitConfigurationId(
        $merchantId,
        $splitConfigurationId,
        $body
    );
    echo 'SplitConfiguration:';
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
  "description": "Updated description for the split configuration",
  "rules": [
    {
      "currency": "ANY",
      "fundingSource": "ANY",
      "paymentMethod": "ANY",
      "ruleId": "SCRL4224P22322585HPCX384JW65VW",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 10,
          "variablePercentage": 50,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 10,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX384JX52M2",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToOneBalanceAccount",
        "tip": "addToOneBalanceAccount"
      }
    },
    {
      "currency": "EUR",
      "fundingSource": "ANY",
      "paymentMethod": "visa",
      "ruleId": "SCRL4224P22322585HPCX5V4KV6L2R",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 100,
          "variablePercentage": 0,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 100,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX5V4KW26C9",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToLiableAccount",
        "tip": "addToLiableAccount"
      }
    }
  ],
  "splitConfigurationId": "SCNF4224P22322585HPCX384JV6JGX"
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


# Delete-Merchants-Merchant Id-Split Configurations-Split Configuration Id-Rules-Rule Id

Deletes the rule specified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function deleteMerchantsMerchantIdSplitConfigurationsSplitConfigurationIdRulesRuleId(
    string $merchantId,
    string $splitConfigurationId,
    string $ruleId
): SplitConfiguration
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `splitConfigurationId` | `string` | Template, Required | The unique identifier of the split configuration. |
| `ruleId` | `string` | Template, Required | - |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfiguration`](../../doc/models/split-configuration.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$splitConfigurationId = 'splitConfigurationId4';

$ruleId = 'ruleId4';

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->deleteMerchantsMerchantIdSplitConfigurationsSplitConfigurationIdRulesRuleId(
        $merchantId,
        $splitConfigurationId,
        $ruleId
    );
    echo 'SplitConfiguration:';
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


# Patch-Merchants-Merchant Id-Split Configurations-Split Configuration Id-Rules-Rule Id

Changes the [split conditions of the rule](https://docs.adyen.com/platforms/automatic-split-configuration/manage-split-configurations/api/#update-condition) specified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function patchMerchantsMerchantIdSplitConfigurationsSplitConfigurationIdRulesRuleId(
    string $merchantId,
    string $splitConfigurationId,
    string $ruleId,
    ?UpdateSplitConfigurationRuleRequest $body = null
): SplitConfiguration
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `splitConfigurationId` | `string` | Template, Required | The identifier of the split configuration. |
| `ruleId` | `string` | Template, Required | The unique identifier of the split configuration rule. |
| `body` | [`?UpdateSplitConfigurationRuleRequest`](../../doc/models/update-split-configuration-rule-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfiguration`](../../doc/models/split-configuration.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$splitConfigurationId = 'splitConfigurationId4';

$ruleId = 'ruleId4';

$body = UpdateSplitConfigurationRuleRequestBuilder::init(
    'EUR',
    'ANY',
    'visa',
    'ANY'
)->build();

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->patchMerchantsMerchantIdSplitConfigurationsSplitConfigurationIdRulesRuleId(
        $merchantId,
        $splitConfigurationId,
        $ruleId,
        $body
    );
    echo 'SplitConfiguration:';
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
  "description": "Your description for the split configuration",
  "rules": [
    {
      "currency": "ANY",
      "fundingSource": "ANY",
      "paymentMethod": "ANY",
      "ruleId": "SCRL4224P22322585HPCX384JW65VW",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 10,
          "variablePercentage": 50,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 10,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX384JX52M2",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToOneBalanceAccount",
        "tip": "addToOneBalanceAccount"
      }
    },
    {
      "currency": "EUR",
      "fundingSource": "ANY",
      "paymentMethod": "visa",
      "ruleId": "SCRL4224P22322585HPCX5V4KV6L2R",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 10,
          "variablePercentage": 50,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 10,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX5V4KW26C9",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToLiableAccount",
        "tip": "addToOneBalanceAccount"
      }
    }
  ],
  "splitConfigurationId": "SCNF4224P22322585HPCX384JV6JGX"
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


# Patch-Merchants-Split Configurations-Rules-Split Logic

Changes the [split logic](https://docs.adyen.com/platforms/automatic-split-configuration/manage-split-configurations/api/#update-split-logic) specified in the path.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API - SplitConfiguration read and write

```php
function patchMerchantsSplitConfigurationsRulesSplitLogic(
    string $merchantId,
    string $splitConfigurationId,
    string $ruleId,
    string $splitLogicId,
    ?UpdateSplitConfigurationLogicRequest $body = null
): SplitConfiguration
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `merchantId` | `string` | Template, Required | The unique identifier of the merchant account. |
| `splitConfigurationId` | `string` | Template, Required | The unique identifier of the split configuration. |
| `ruleId` | `string` | Template, Required | The unique identifier of the split configuration rule. |
| `splitLogicId` | `string` | Template, Required | The unique identifier of the split configuration split. |
| `body` | [`?UpdateSplitConfigurationLogicRequest`](../../doc/models/update-split-configuration-logic-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`SplitConfiguration`](../../doc/models/split-configuration.md)

## Example Usage

```php
$merchantId = 'merchantId6';

$splitConfigurationId = 'splitConfigurationId4';

$ruleId = 'ruleId4';

$splitLogicId = 'splitLogicId4';

$body = UpdateSplitConfigurationLogicRequestBuilder::init(
    Commission1Builder::init()
        ->fixedAmount(100)
        ->variablePercentage(100)
        ->build()
)
    ->additionalCommission(
        AdditionalCommission1Builder::init()
            ->balanceAccountId('BA3227C223222H5HQ2XX77VVH')
            ->fixedAmount(100)
            ->variablePercentage(0)
            ->build()
    )
    ->chargeback(BehaviorEnum::DEDUCTFROMLIABLEACCOUNT)
    ->paymentFee(PaymentFeeEnum::DEDUCTFROMLIABLEACCOUNT)
    ->remainder(RemainderEnum::ADDTOLIABLEACCOUNT)
    ->tip(TipEnum::ADDTOLIABLEACCOUNT)
    ->build();

$splitConfigurationMerchantLevelApi = $client->getSplitConfigurationMerchantLevelApi();

try {
    $result = $splitConfigurationMerchantLevelApi->patchMerchantsSplitConfigurationsRulesSplitLogic(
        $merchantId,
        $splitConfigurationId,
        $ruleId,
        $splitLogicId,
        $body
    );
    echo 'SplitConfiguration:';
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
  "description": "Your description for the split configuration",
  "rules": [
    {
      "currency": "ANY",
      "fundingSource": "ANY",
      "paymentMethod": "ANY",
      "ruleId": "SCRL4224P22322585HPCX384JW65VW",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 10,
          "variablePercentage": 50,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 10,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX384JX52M2",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToOneBalanceAccount",
        "tip": "addToOneBalanceAccount"
      }
    },
    {
      "currency": "EUR",
      "fundingSource": "ANY",
      "paymentMethod": "visa",
      "ruleId": "SCRL4224P22322585HPCX5V4KV6L2R",
      "shopperInteraction": "ANY",
      "splitLogic": {
        "additionalCommission": {
          "fixedAmount": 100,
          "variablePercentage": 0,
          "balanceAccountId": "BA3227C223222H5HQ2XX77VVH"
        },
        "chargeback": "deductFromLiableAccount",
        "commission": {
          "fixedAmount": 100,
          "variablePercentage": 100
        },
        "splitLogicId": "SCLG4224P22322585HPCX5V4KW26C9",
        "paymentFee": "deductFromLiableAccount",
        "remainder": "addToLiableAccount",
        "tip": "addToLiableAccount"
      }
    }
  ],
  "splitConfigurationId": "SCNF4224P22322585HPCX384JV6JGX"
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

