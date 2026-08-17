# API

```php
$aPI = $client->getAPI();
```

## Class Name

`API`

## Methods

* [Login Request](../../doc/controllers/api.md#login-request)
* [Logout Request](../../doc/controllers/api.md#logout-request)
* [Enable Service Request](../../doc/controllers/api.md#enable-service-request)
* [Admin Request](../../doc/controllers/api.md#admin-request)
* [Payment Request](../../doc/controllers/api.md#payment-request)
* [Card Acquisition Request](../../doc/controllers/api.md#card-acquisition-request)
* [Stored Value Request](../../doc/controllers/api.md#stored-value-request)
* [Reversal Request](../../doc/controllers/api.md#reversal-request)
* [Reconciliation Request](../../doc/controllers/api.md#reconciliation-request)
* [Get Totals Request](../../doc/controllers/api.md#get-totals-request)
* [Balance Inquiry Request](../../doc/controllers/api.md#balance-inquiry-request)
* [Transaction Status Request](../../doc/controllers/api.md#transaction-status-request)
* [Abort Request](../../doc/controllers/api.md#abort-request)
* [Diagnosis Request](../../doc/controllers/api.md#diagnosis-request)
* [Display Request](../../doc/controllers/api.md#display-request)
* [Input Request](../../doc/controllers/api.md#input-request)
* [Print Request](../../doc/controllers/api.md#print-request)
* [Card Reader APDU Request](../../doc/controllers/api.md#card-reader-apdu-request)


# Login Request

It conveys information related to the session (period between a Login and the following Logout) to process.
Content of the `LoginRequest` message.

```php
function loginRequest(?LoginRequest $body = null): LoginResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?LoginRequest`](../../doc/models/login-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys Information related to the Login to process.
Content of the Login Response message.

[`LoginResponse`](../../doc/models/login-response.md)

## Example Usage

```php
$body = LoginRequestBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    SaleSoftware1Builder::init(
        'ManufacturerID4',
        'ApplicationName8',
        'SoftwareVersion0',
        'CertificationCode4'
    )->build(),
    'OperatorLanguage2'
)
    ->trainingModeFlag(false)
    ->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->loginRequest($body);
    echo 'LoginResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Logout Request

Empty.
Content of the Logout Request message.

```php
function logoutRequest(?LogoutRequest $body = null): LogoutResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?LogoutRequest`](../../doc/models/logout-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys the result of the Logout.
Content of the Logout Response message.

[`LogoutResponse`](../../doc/models/logout-response.md)

## Example Usage

```php
$body = LogoutRequestBuilder::init()
    ->maintenanceAllowed(false)
    ->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->logoutRequest($body);
    echo 'LogoutResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Enable Service Request

It conveys the services that will be enabled for the POI Terminal without the request of the Sale System, and a possible invitation for the Customer to start the services.
Content of the Enable Service Request message.

```php
function enableServiceRequest(?EnableServiceRequest $body = null): EnableServiceResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?EnableServiceRequest`](../../doc/models/enable-service-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys the result of the Enable Service processing.
Content of the Enable Service Response message.

[`EnableServiceResponse`](../../doc/models/enable-service-response.md)

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->enableServiceRequest();
    echo 'EnableServiceResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Admin Request

Empty.
Content of the Custom Admin Request message.

```php
function adminRequest(?AdminRequest $body = null): AdminResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?AdminRequest`](../../doc/models/admin-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys the result of the Custom Admin.
Content of the Custom Admin Response message.

[`AdminResponse`](../../doc/models/admin-response.md)

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->adminRequest();
    echo 'AdminResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Payment Request

Request sent to terminal to initiate payment.
It conveys Information related to the Payment transaction to process.
Content of the `PaymentRequest` message.

```php
function paymentRequest(?PaymentRequest2 $body = null): PaymentResponse4
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?PaymentRequest2`](../../doc/models/payment-request-2.md) | Body, Optional | - |

## Response Type

**200**: It conveys Information related to the Payment transaction processed by the POI System.
Content of the Payment Response message.

[`PaymentResponse4`](../../doc/models/payment-response-4.md)

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->paymentRequest();
    echo 'PaymentResponse4:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Card Acquisition Request

It conveys Information related to the payment and loyalty cards to read and analyse. This message pair is usually followed by a message pair (e.g. payment or loyalty) which refers to this Card Acquisition message pair.
Content of the Card Acquisition Request message.

```php
function cardAcquisitionRequest(?CardAcquisitionRequest $body = null): CardAcquisitionResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CardAcquisitionRequest`](../../doc/models/card-acquisition-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys Information related to the payment and loyalty cards read and processed by the POI System and entered by the Customer.
Content of the Card Acquisition Response message.

[`CardAcquisitionResponse`](../../doc/models/card-acquisition-response.md)

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->cardAcquisitionRequest();
    echo 'CardAcquisitionResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Stored Value Request

It conveys Information related to the Stored Value transaction to process.
Content of the Stored Value Request message.

```php
function storedValueRequest(?StoredValueRequest $body = null): StoredValueResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?StoredValueRequest`](../../doc/models/stored-value-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys Information related to the Stored Value transaction processed by the POI System.
Content of the Stored Value Response message.

[`StoredValueResponse`](../../doc/models/stored-value-response.md)

## Example Usage

```php
$body = StoredValueRequestBuilder::init(
    SaleData1Builder::init(
        TransactionIDType1Builder::init(
            'TransactionID2',
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
        )->build()
    )->build(),
    [
        StoredValueDataBuilder::init(
            StoredValueTransactionType1Enum::RESERVE
        )->build()
    ]
)->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->storedValueRequest($body);
    echo 'StoredValueResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Reversal Request

It conveys Information related to the reversal of a previous payment or a loyalty transaction.
Content of the Reversal Request message.

```php
function reversalRequest(?ReversalRequest $body = null): ReversalResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?ReversalRequest`](../../doc/models/reversal-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys Information related to the reversal processed by the POI System.
Content of the Reversal Response message.

[`ReversalResponse`](../../doc/models/reversal-response.md)

## Example Usage

```php
$body = ReversalRequestBuilder::init(
    OriginalPOITransaction2Builder::init()
        ->reuseCardDataFlag(true)
        ->build(),
    ReversalReason1Enum::CUSTCANCEL
)->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->reversalRequest($body);
    echo 'ReversalResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Reconciliation Request

Content of the Reconciliation Request message.
It conveys Information related to the Reconciliation requested by the Sale System.

```php
function reconciliationRequest(?ReconciliationRequest $body = null): ReconciliationResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?ReconciliationRequest`](../../doc/models/reconciliation-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys Information related to the Reconciliation transaction processed by the POI System.
Content of the Reconciliation Response message.

[`ReconciliationResponse`](../../doc/models/reconciliation-response.md)

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->reconciliationRequest();
    echo 'ReconciliationResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Get Totals Request

It conveys information from the Sale System related to the scope and the format of the totals to be computed by the POI System.
Content of the Get Totals Request message.

```php
function getTotalsRequest(?GetTotalsRequest $body = null): GetTotalsResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?GetTotalsRequest`](../../doc/models/get-totals-request.md) | Body, Optional | - |

## Response Type

**200**: Content of the Reconciliation Response message.
It conveys Information related to the Reconciliation transaction processed by the POI System.

[`GetTotalsResponse`](../../doc/models/get-totals-response.md)

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->getTotalsRequest();
    echo 'GetTotalsResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Balance Inquiry Request

It conveys Information related to the account for which a Balance Inquiry is requested.
Content of the Balance Inquiry Request message.

```php
function balanceInquiryRequest(?BalanceInquiryRequest $body = null): BalanceInquiryResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?BalanceInquiryRequest`](../../doc/models/balance-inquiry-request.md) | Body, Optional | - |

## Response Type

**200**: Content of the Balance Inquiry Response message.
It conveys the balance and the identification of the associated payment, loyalty or stored value account.

[`BalanceInquiryResponse`](../../doc/models/balance-inquiry-response.md)

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->balanceInquiryRequest();
    echo 'BalanceInquiryResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Transaction Status Request

Content of the TransactionStatus Request message.
It conveys Information requested for status of the last or current Payment, Loyalty or Reversal transaction.

```php
function transactionStatusRequest(?TransactionStatusRequest $body = null): TransactionStatusResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?TransactionStatusRequest`](../../doc/models/transaction-status-request.md) | Body, Optional | - |

## Response Type

**200**: Content of the TransactionStatus Response message.
It conveys Information related to the status of the last or current Payment, Loyalty or Reversal transaction.

[`TransactionStatusResponse`](../../doc/models/transaction-status-response.md)

## Example Usage

```php
$body = TransactionStatusRequestBuilder::init()
    ->receiptReprintFlag(false)
    ->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->transactionStatusRequest($body);
    echo 'TransactionStatusResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Abort Request

Body of the Abort Request message.
It conveys Information requested for identification of the message request carrying the transaction to abort. A message to display on the CustomerError Device could be sent by the Sale System (DisplayOutput).

```php
function abortRequest(?AbortRequest $body = null): array
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?AbortRequest`](../../doc/models/abort-request.md) | Body, Optional | - |

## Response Type

**200**: A successful `AbortRequest` returns a response with a **200 OK** HTTP status code and no body.

`array`

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->abortRequest();
    echo 'array:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Diagnosis Request

It conveys Information related to the target POI for which the diagnosis is requested.
Content of the Diagnosis Request message.

```php
function diagnosisRequest(?DiagnosisRequest $body = null): DiagnosisResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DiagnosisRequest`](../../doc/models/diagnosis-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys the result of the requested diagnosis and a possible message to display on a logical device.
Content of the Diagnosis Response message.

[`DiagnosisResponse`](../../doc/models/diagnosis-response.md)

## Example Usage

```php
$body = DiagnosisRequestBuilder::init()
    ->hostDiagnosisFlag(false)
    ->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->diagnosisRequest($body);
    echo 'DiagnosisResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Display Request

It conveys the data to display and the way to process the display. It contains the complete content to display. It might contain an operation (the DisplayOutput element) per Display Device type.
Content of the Display Request message.

```php
function displayRequest(?DisplayRequest $body = null): DisplayResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?DisplayRequest`](../../doc/models/display-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys the result of the display, parallel to the message request, except if response not required and absent.
Content of the Display Response message.

[`DisplayResponse`](../../doc/models/display-response.md)

## Example Usage

```php
$body = DisplayRequestBuilder::init(
    [
        DisplayOutputBuilder::init(
            Device11Enum::CASHIERDISPLAY,
            InfoQualify1Enum::STATUS,
            OutputContent1Builder::init(
                OutputFormat1Enum::XHTML
            )->build()
        )
            ->responseRequiredFlag(true)
            ->minimumDisplayTime(0)
            ->build()
    ]
)->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->displayRequest($body);
    echo 'DisplayResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Input Request

Content of the `InputRequest` message. It conveys the data to display and how to process it. In addition to the display on the Input Device, it might contain an operation (the `DisplayOutput` element) per Display Device type.

```php
function inputRequest(?InputRequest $body = null): InputResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?InputRequest`](../../doc/models/input-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys the result of the input or the result of the outputs, parallel to the message request, except if response not required and absent.
Content of the Input Response message.

[`InputResponse`](../../doc/models/input-response.md)

## Example Usage

```php
$body = InputRequestBuilder::init(
    InputData2Builder::init(
        Device2Enum::CASHIERDISPLAY,
        InfoQualify2Enum::CUSTOMERASSISTANCE,
        InputCommand1Enum::GETANYKEY
    )
        ->notifyCardInputFlag(false)
        ->immediateResponseFlag(false)
        ->waitUserValidationFlag(true)
        ->fromRightToLeftFlag(false)
        ->maskCharactersFlag(false)
        ->beepKeyFlag(false)
        ->globalCorrectionFlag(false)
        ->disableCancelFlag(false)
        ->disableCorrectFlag(false)
        ->disableValidFlag(false)
        ->menuBackFlag(false)
        ->build()
)->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->inputRequest($body);
    echo 'InputResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Print Request

Content of the Print Request message.
It conveys the complete data to print and how to process the print.

```php
function printRequest(?PrintRequest $body = null): PrintResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?PrintRequest`](../../doc/models/print-request.md) | Body, Optional | - |

## Response Type

**200**: It conveys the result of the print, parallel to the message request, except if response not required and absent.
Content of the Print Response message.

[`PrintResponse`](../../doc/models/print-response.md)

## Example Usage

```php
$body = PrintRequestBuilder::init(
    PrintOutput2Builder::init(
        DocumentQualifier2Enum::CUSTOMERRECEIPT,
        ResponseMode1Enum::PRINTEND,
        OutputContent3Builder::init(
            OutputFormat1Enum::XHTML
        )->build()
    )
        ->integratedPrintFlag(false)
        ->requiredSignatureFlag(false)
        ->build()
)->build();

$aPI = $client->getAPI();

try {
    $result = $aPI->printRequest($body);
    echo 'PrintResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```


# Card Reader APDU Request

It contains the APDU request to send to the chip of the card, and a possible invitation message to display on the CashierInterface or the CustomerInterface.
Content of the Card Reader APDU Request message.

```php
function cardReaderAPDURequest(?CardReaderAPDURequest $body = null): CardReaderAPDUResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?CardReaderAPDURequest`](../../doc/models/card-reader-apdu-request.md) | Body, Optional | - |

## Response Type

**200**: Content of the Card Reader APDU Response message.
It contains the result of the requested service, APDU response sent by the chip of the card in response to the APDU request.

[`CardReaderAPDUResponse`](../../doc/models/card-reader-apdu-response.md)

## Example Usage

```php
$aPI = $client->getAPI();

try {
    $result = $aPI->cardReaderAPDURequest();
    echo 'CardReaderAPDUResponse:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

