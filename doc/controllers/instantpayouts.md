# Instantpayouts

```php
$instantpayoutsApi = $client->getInstantpayoutsApi();
```

## Class Name

`InstantpayoutsApi`


# Post-Payout

> This endpoint is **deprecated** and no longer supports new integrations. Do one of the following:
> 
> - If you are building a new integration, use the POST [/transfers](https://docs.adyen.com/api-explorer/transfers/latest/post/transfers) endpoint instead.
> - If you are already using the Payout API, reach out to your Adyen contact to learn how to migrate to the Transfers API.
> 
> With the Transfers API, you can:
> 
> - Handle multiple payout use cases with a single API.
> - Use new payout functionalities, such as instant payouts to bank accounts.
> - Receive webhooks with more details and defined transfer states.
> 
> For more information about the payout features of the Transfers API, see our [Payouts](https://docs.adyen.com/payouts/payout-service) documentation.

With this call, you can pay out to your customers, and funds will be made available within 30 minutes on the cardholder's bank account (this is dependent on whether the issuer supports this functionality). Instant card payouts are only supported for Visa and Mastercard cards.

```php
function postPayout(?PayoutRequest $body = null): PayoutResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?PayoutRequest`](../../doc/models/payout-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`PayoutResponse`](../../doc/models/payout-response.md)

## Example Usage

```php
$body = PayoutRequestBuilder::init(
    AmountBuilder::init(
        'USD',
        2500
    )->build(),
    'YOUR_MERCHANT_ACCOUNT',
    'P9999999999999999'
)
    ->billingAddress(
        AddressBuilder::init(
            'Beverly Hills',
            'US',
            '121',
            '90210',
            'Brannan Street'
        )
            ->stateOrProvince('CA')
            ->build()
    )
    ->card(
        CardBuilder::init()
            ->expiryMonth('03')
            ->expiryYear('2030')
            ->holderName('John Smith')
            ->number('4111111111111111')
            ->build()
    )
    ->shopperName(
        NameBuilder::init(
            'John',
            'Smith'
        )->build()
    )->build();

$instantPayoutsApi = $client->getInstantPayoutsApi();

try {
    $result = $instantPayoutsApi->postPayout($body);
    echo 'PayoutResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request - a problem reading or understanding the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 401 | Unauthorized - authentication required. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`ServiceErrorException`](../../doc/models/service-error-exception.md) |

