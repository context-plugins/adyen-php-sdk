# Authorizedcardusers

```php
$authorizedcardusersApi = $client->getAuthorizedcardusersApi();
```

## Class Name

`AuthorizedcardusersApi`

## Methods

* [Get-Payment Instruments-Payment Instrument Id-Authorised Card Users](../../doc/controllers/authorizedcardusers.md#get-payment-instruments-payment-instrument-id-authorised-card-users)
* [Post-Payment Instruments-Payment Instrument Id-Authorised Card Users](../../doc/controllers/authorizedcardusers.md#post-payment-instruments-payment-instrument-id-authorised-card-users)
* [Delete-Payment Instruments-Payment Instrument Id-Authorised Card Users](../../doc/controllers/authorizedcardusers.md#delete-payment-instruments-payment-instrument-id-authorised-card-users)
* [Patch-Payment Instruments-Payment Instrument Id-Authorised Card Users](../../doc/controllers/authorizedcardusers.md#patch-payment-instruments-payment-instrument-id-authorised-card-users)


# Get-Payment Instruments-Payment Instrument Id-Authorised Card Users

Returns the authorized users for a card.

:information_source: **Note** This endpoint does not require authentication.

```php
function getPaymentInstrumentsPaymentInstrumentIdAuthorisedCardUsers(
    string $paymentInstrumentId
): AuthorisedCardUsers
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Template, Required | - |

## Response Type

**200**: Successful operation

[`AuthorisedCardUsers`](../../doc/models/authorised-card-users.md)

## Example Usage

```php
$paymentInstrumentId = 'paymentInstrumentId2';

$authorizedCardUsersApi = $client->getAuthorizedCardUsersApi();

try {
    $result = $authorizedCardUsersApi->getPaymentInstrumentsPaymentInstrumentIdAuthorisedCardUsers($paymentInstrumentId);
    echo 'AuthorisedCardUsers:';
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
  "legalEntityIds": [
    "LE328V522322685LV3KTNF35M",
    "LE328SW223226B5LWVWNQ8THN"
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 404 | Not Found | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Payment Instruments-Payment Instrument Id-Authorised Card Users

Assigns authorized users to a card. Users must have the **authorisedPaymentInstrumentUser** capability to be able to use the card.

:information_source: **Note** This endpoint does not require authentication.

```php
function postPaymentInstrumentsPaymentInstrumentIdAuthorisedCardUsers(
    string $paymentInstrumentId,
    AuthorisedCardUsers $body
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Template, Required | - |
| `body` | [`AuthorisedCardUsers`](../../doc/models/authorised-card-users.md) | Body, Required | - |

## Response Type

**204**: Successful operation

`void`

## Example Usage

```php
$paymentInstrumentId = 'paymentInstrumentId2';

$body = AuthorisedCardUsersBuilder::init()
    ->legalEntityIds(
        [
            'LE328V522322685LV3KTNF35M',
            'LE328SW223226B5LWVWNQ8THN'
        ]
    )
    ->build();

$authorizedCardUsersApi = $client->getAuthorizedCardUsersApi();

try {
    $authorizedCardUsersApi->postPaymentInstrumentsPaymentInstrumentIdAuthorisedCardUsers(
        $paymentInstrumentId,
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
| 400 | Bad request | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Payment Instruments-Payment Instrument Id-Authorised Card Users

Deletes the list of authorized users assigned to a card.

:information_source: **Note** This endpoint does not require authentication.

```php
function deletePaymentInstrumentsPaymentInstrumentIdAuthorisedCardUsers(string $paymentInstrumentId): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Template, Required | - |

## Response Type

**204**: Successful operation

`void`

## Example Usage

```php
$paymentInstrumentId = 'paymentInstrumentId2';

$authorizedCardUsersApi = $client->getAuthorizedCardUsersApi();

try {
    $authorizedCardUsersApi->deletePaymentInstrumentsPaymentInstrumentIdAuthorisedCardUsers($paymentInstrumentId);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Patch-Payment Instruments-Payment Instrument Id-Authorised Card Users

Updates the list of authorized users for a card.

> This request replaces all existing authorized users for the card.

:information_source: **Note** This endpoint does not require authentication.

```php
function patchPaymentInstrumentsPaymentInstrumentIdAuthorisedCardUsers(
    string $paymentInstrumentId,
    AuthorisedCardUsers $body
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentInstrumentId` | `string` | Template, Required | - |
| `body` | [`AuthorisedCardUsers`](../../doc/models/authorised-card-users.md) | Body, Required | - |

## Response Type

**204**: Successful operation

`void`

## Example Usage

```php
$paymentInstrumentId = 'paymentInstrumentId2';

$body = AuthorisedCardUsersBuilder::init()
    ->legalEntityIds(
        [
            'LE328V522322685LV3KTNF35M',
            'LE328SW223226B5LWVWNQ8THN'
        ]
    )
    ->build();

$authorizedCardUsersApi = $client->getAuthorizedCardUsersApi();

try {
    $authorizedCardUsersApi->patchPaymentInstrumentsPaymentInstrumentIdAuthorisedCardUsers(
        $paymentInstrumentId,
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
| 400 | Bad request | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

