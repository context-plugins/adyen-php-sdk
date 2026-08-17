# Account Verification

```php
$accountVerificationApi = $client->getAccountVerificationApi();
```

## Class Name

`AccountVerificationApi`

## Methods

* [Get-Account Verification-Reports-Code](../../doc/controllers/account-verification.md#get-account-verification-reports-code)
* [Post-Account Verification-Routes](../../doc/controllers/account-verification.md#post-account-verification-routes)


# Get-Account Verification-Reports-Code

Get the account verification report using a unique code from a successful open banking connection. This report provides identity verification and bank account details.

:information_source: **Note** This endpoint does not require authentication.

```php
function getAccountVerificationReportsCode(string $code): AccountVerificationReportResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `string` | Template, Required | The unique code you receive after a successful open banking flow that is included as a query parameter in the `redirectUrl` callback.<br><br>**Constraints**: *Minimum Length*: `1` |

## Response Type

**200**: OK - The request has succeeded.

[`AccountVerificationReportResponse`](../../doc/models/account-verification-report-response.md)

## Example Usage

```php
$code = 'code8';

$accountVerificationApi = $client->getAccountVerificationApi();

try {
    $result = $accountVerificationApi->getAccountVerificationReportsCode($code);
    echo 'AccountVerificationReportResponse:';
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
  "id": "nJwJE68h6vlSEnk",
  "country": "US",
  "accounts": [
    {
      "accountId": "XvNzLGMpl3fBevllWEwks3jvBvPy88sbkypkP",
      "accountType": "CURRENT",
      "accountName": "Plaid Gold Standard 0% Interest Checking",
      "accountNumber": "1111222233330000",
      "currency": "USD",
      "identifiers": {
        "ach": {
          "accountNumber": "1111222233330000",
          "routingNumber": "011401533"
        }
      },
      "parties": [
        {
          "identity": {
            "fullLegalName": "Jane Doe",
            "name": "Jane Doe"
          },
          "role": "HOLDER"
        }
      ],
      "bankName": "Wells Fargo"
    },
    {
      "accountId": "XvNzLGMpl3fBevllWEwks3jvBvPy88sbkypkP",
      "accountType": "CURRENT",
      "accountName": "Plaid Gold Standard 0% Interest Checking",
      "accountNumber": "3333222211110000",
      "currency": "USD",
      "identifiers": {
        "ach": {
          "accountNumber": "3333222211110000",
          "routingNumber": "033587521"
        }
      },
      "parties": [
        {
          "identity": {
            "fullLegalName": "Jane Doe",
            "name": "Jane Doe"
          },
          "role": "HOLDER"
        }
      ],
      "bankName": "Bank of America"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request is malformed or is not in the expected format. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - The API credential used in the request is invalid or does not have the right permissions. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found - The entity was not found. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 429 | Too Many Requests - Request rate limit exceeded. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Service Error - An unrecoverable error occurred while trying to perform the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Account Verification-Routes

Create a list of routes for verifying bank accounts of third-party individuals. Successful connections generate a unique code used for requesting bank reports and verifying identity.

:information_source: **Note** This endpoint does not require authentication.

```php
function postAccountVerificationRoutes(
    AccountVerificationRoutesRequest $body
): AccountVerificationRoutesResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AccountVerificationRoutesRequest`](../../doc/models/account-verification-routes-request.md) | Body, Required | - |

## Response Type

**200**: OK - The request has succeeded.

[`AccountVerificationRoutesResponse`](../../doc/models/account-verification-routes-response.md)

## Example Usage

```php
$body = AccountVerificationRoutesRequestBuilder::init(
    AccountVerificationCountry2Enum::NL,
    'https://merchanturl.example.org/redirect/url'
)
    ->locale('en-US')
    ->state('11a1e60a-18b0-4dda-9258-e0ae29e1e2a3')
    ->build();

$accountVerificationApi = $client->getAccountVerificationApi();

try {
    $result = $accountVerificationApi->postAccountVerificationRoutes($body);
    echo 'AccountVerificationRoutesResponse:';
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
  "routes": [
    {
      "provider": {
        "name": "Tink",
        "logoURL": "https://obgateway.adyen.com/obgateway/static/provider/images/tink-logo.svg"
      },
      "link": "https://obgateway.adyen.com/obgateway/provider/outgoing/tink/redirect/13ec4802-c987-4f8c-8909-9a75ff567256"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - The request is malformed or is not in the expected format. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - The API credential used in the request is invalid or does not have the right permissions. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 429 | Too Many Requests - Request rate limit exceeded. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Service Error - An unrecoverable error occurred while trying to perform the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

