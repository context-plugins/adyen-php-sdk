# Orders

```php
$ordersApi = $client->getOrdersApi();
```

## Class Name

`OrdersApi`

## Methods

* [Post-Orders](../../doc/controllers/orders.md#post-orders)
* [Post-Orders-Cancel](../../doc/controllers/orders.md#post-orders-cancel)
* [Post-Payment Methods-Balance](../../doc/controllers/orders.md#post-payment-methods-balance)


# Post-Orders

Creates an order to be used for partial payments. Make a POST `/orders` call before making a `/payments` call when processing payments with different payment methods.

```php
function postOrders(?string $idempotencyKey = null, ?CreateOrderRequest $body = null): CreateOrderResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotencyKey` | `?string` | Header, Optional | A unique identifier for the message with a maximum of 64 characters (we recommend a UUID). |
| `body` | [`?CreateOrderRequest`](../../doc/models/create-order-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CreateOrderResponse`](../../doc/models/create-order-response.md)

## Example Usage

```php
$body = CreateOrderRequestBuilder::init(
    Amount21Builder::init(
        'EUR',
        2500
    )->build(),
    'YOUR_MERCHANT_ACCOUNT',
    'YOUR_ORDER_REFERENCE'
)->build();

$ordersApi = $client->getOrdersApi();

try {
    $result = $ordersApi->postOrders(
        null,
        $body
    );
    echo 'CreateOrderResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "8616178914061985",
  "resultCode": "Success",
  "expiresAt": "2021-04-09T14:16:46Z",
  "orderData": "Ab02b4c0!BQABAgCxXvknCldOcRElkxY8Za7iyym4Wv8aDzyNwmj/3nh4G6YtwnUIJHaK62NlN4oIsACdkn1FEjBwKlheG40jvXcYGBk4KFV5WvOhTVCpv/KXnkrI7xQv/u2lE7U4wA+HPB6K4Zj2L8xO/ogZi+zGZqFs5m16jmkH7ku6FzXygXLNuUCuOlmlXSZhdkHHTNVQSq1MELDK9OL74y532ETRPTCNxx8WlEiZB+LDqYrPvH9GgigtD5kw8Do45jfFfG72kWBEgfYqp4mbUmBB9ebXFYZKfF0qvW1x7A2Y9+/MFlTIdXfKW484bJeDBCTTrmKGXIj+U4r5imr5fXTyNLcrxyUqwrb9jg+5B4qg1XB6Cgj5UPlSI4O62I7v0s5TTj69dzLwUQRxSQbwLrZVGYavXzeVKI54BVLRV3d/+BbPvTqnTo34UhfZbPlOx9F2eyaS0ZXdOKnHw89uGUgxUpLsMqnbRysi/pxpZaulel+0mExb68wVxb/7Teob5eRG4gp7cfZVZs6tLXOYWL+W0TqIlsa3hWsfM0LeaovzkoDtW/pK5JABXwMtLig9tsxoEh9ONYtIzkXC21LZ8ebiuSIMaPizjF8yca+QxrCZalQsu6uKnBz/mm8nnsflaGU2QS5zcoxk1RudL1Bl36LM9UZGPpFEYWiYA4sUsnNLw7peJjWCGhDepnwMv4TlgsEtoDtz1T54AEp7ImtleSI6IkFGMEFBQTEwM0NBNTM3RUFFRDg3QzI0REQ1MzkwOUI4MEE3OEE5MjNFMzgyM0Q2OERBQ0M5NEI5RkY4MzA1REMifRslOdmfgUHTXl66WPD9xoW2whIeRx/jR++2MqNE16x6zQy+KtDN8/h60crZwmqkjVTQYqQlsYSYDHSIyb4wnnay16/5il1yS7vN3UCLaTXjYBIAyyx6Wr9j4P3CI/etB+PpviHoESC4mV6ZN4whMDQyziQ8s230GtboXbh42qND7rk9phySBogowQlXrtF+l2n2F46nyif0owEgik5fGARfvjZtY2w23s30KMLNwU4gWSvX4H6RMVS8TfZH2fKfNrwB3tZUXwYkELs5ntaHysswq5Mn5aq2BKAMHu/Rh/wureMSI73Qi0avjrzWCwzt3JH4wnzErMnOZwSdgA==",
  "reference": "shopper-reference-ekvL83",
  "remainingAmount": {
    "currency": "EUR",
    "value": 2500
  },
  "amount": {
    "currency": "EUR",
    "value": 300
  }
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


# Post-Orders-Cancel

Cancels an order. Cancellation of an order results in an automatic rollback of all payments made in the order, either by canceling or refunding the payment, depending on the type of payment method.

```php
function postOrdersCancel(?string $idempotencyKey = null, ?CancelOrderRequest $body = null): CancelOrderResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotencyKey` | `?string` | Header, Optional | A unique identifier for the message with a maximum of 64 characters (we recommend a UUID). |
| `body` | [`?CancelOrderRequest`](../../doc/models/cancel-order-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`CancelOrderResponse`](../../doc/models/cancel-order-response.md)

## Example Usage

```php
$body = CancelOrderRequestBuilder::init(
    'YOUR_MERCHANT_ACCOUNT',
    EncryptedOrderData4Builder::init(
        '823fh892f8f18f4...148f13f9f3f',
        '8815517812932012'
    )->build()
)->build();

$ordersApi = $client->getOrdersApi();

try {
    $result = $ordersApi->postOrdersCancel(
        null,
        $body
    );
    echo 'CancelOrderResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "8816178914079738",
  "resultCode": "Received"
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


# Post-Payment Methods-Balance

Retrieves the balance remaining on a shopper's gift card. To check a gift card's balance, make a POST `/paymentMethods/balance` call and include the gift card's details inside a `paymentMethod` object.

```php
function postPaymentMethodsBalance(
    ?string $idempotencyKey = null,
    ?BalanceCheckRequest $body = null
): BalanceCheckResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `idempotencyKey` | `?string` | Header, Optional | A unique identifier for the message with a maximum of 64 characters (we recommend a UUID). |
| `body` | [`?BalanceCheckRequest`](../../doc/models/balance-check-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`BalanceCheckResponse`](../../doc/models/balance-check-response.md)

## Example Usage

```php
$body = BalanceCheckRequestBuilder::init(
    Amount2Builder::init(
        'EUR',
        1000
    )->build(),
    'YOUR_MERCHANT_ACCOUNT',
    [
        'type' => 'givex',
        'number' => '4126491073027401',
        'cvc' => '737'
    ]
)->build();

$ordersApi = $client->getOrdersApi();

try {
    $result = $ordersApi->postPaymentMethodsBalance(
        null,
        $body
    );
    echo 'BalanceCheckResponse:';
    var_dump($result);
} catch (ServiceErrorException $exp) {
    echo 'Caught ServiceErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "pspReference": "KHQC5N7G84BLNK43",
  "resultCode": "Success",
  "balance": {
    "currency": "EUR",
    "value": 5000
  }
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

